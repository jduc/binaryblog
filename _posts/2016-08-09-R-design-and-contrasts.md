---
layout: default
title:  "R Design matrix and contrasts"
categories: R
description: "Quick intro on how to use the sqldf R package"
---

# R Design matrix and contrasts
Here, I will try to explain by example how the design and matrix work in R

## The data
In our example we have 6 Groups, JE, JK, DE, DK, TE, TK. *K* and *E* stands for the KAP1 KO or not,
and the *J*,*D* and *T* stands for another type of KO. The idea, is to find out how the KAP1 KO
affect each *J*, *D* independently and *T* and in a second time, see if the KAP1 KO is different in
other experiment. This can be done easy using linear modeling.

## Modeling
As usual our model is in the form:
$$y = \boldsymbol{\beta}X$$  with $$\beta$$ being the estimators and X the gating variables. 

In our case, we can model it in R using a factor for the Kap1 and another one for the other KO. Once
we have those, we can use the model.matrix function to create the model with confounding. 



```R
#compute test
kap1 <- relevel(as.factor(ifelse(grepl('K', colnames(countTable)), 'KO', 'WT')), "WT")
cell <- relevel(as.factor(ifelse(grepl('D', colnames(countTable)), 'dnmt', 
                         ifelse(grepl('T', colnames(countTable)), 'tet', 'J1'))), 'J1')
design <- model.matrix(~ -1 + cell*kap1)
contrasts <- cbind(c(0,0,0,0,1,0), c(0,0,0,0,0,1))
fit1 <- lmFit(v, design)
design.group <- model.matrix(~ -1 + Group)
```

> Note that the order of the factor matters in model.matrix, also it's important to relevel
correctly. Also we use the -1 trick to get rid of the intercept

This results in a formulation of the type: 

$$
y = \beta_1J + \beta_2D + \beta_3T + \beta_4KAP + \beta_5D\&KAP + \beta_6T\&KAP
$$

Which can be represented like this: 

![Modeling]({{ site.baseurl }}/assets/2016-08-09-design.svg)


The 3 first betas are the average of the J D and T groups, the $$\beta_4$$ is the effect of KAP1 on
the reference which is *J1* (as we relevel the factor). $$\beta_5$$ is the effect of being in *D*
and *KAP1*, in other term it's the difference between $$\beta_4$$ and $$\beta_2$$. Concordantly,
$$\beta_6$$ is the difference in KAP1 for the *T* group.

So, if one were to compute the mean of for instance *D* and *KAP* group, it would be: 
$$
\beta_2 + \beta_4 + \beta_5
$$

## Contrasts
Now regarding contrasts, for instance testing the KAP1 effect in J, we can simply test for: 

```R
contrast <- c(0, 0, 0, 1, 0, 0)
```

For testing the effect of KAP1 in *D*, one can test using: 
$$
\beta_2 = \beta_2 + \beta_4 + \beta_5
$$

Which simplifies to 

```R
contrast <- c(0, 0, 0, 1, 1, 0)
```

Finally, for the contrast of what is the effect of KAP1 in *D* compared to in *J*, we can directly
use the contrast: 

```R
contrast <- c(0, 0, 0, 0, 1, 0)
```
