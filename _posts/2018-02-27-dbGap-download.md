---
layout: default
title:  "Download secure data on dbGap"
categories: bash
description: "How to download data from dbGap using sratoolkit prefetch"
---

# dbGap: the nightmare
The [dbGap website](https://dbgap.ncbi.nlm.nih.gov) is a nightmare. It's slow, it's not convenient
and it's always down... To avoid losing time and minimize time on this website, here are the
pitfalls: 

## 1. Login
Every who knows who many month's, the password is reset. When it does, you don't know, login fails
and you panic. You have to change it on a different website to make it work again, it's
[there](https://public.era.nih.gov/commons/commonsInit.do).

## 2. Project key
Once logged in, go to "My Projects" tab and download the project key (under Actions on the right,
bottom button).

## 2.a get the cart
If you want to get the cart data, you can in the sra selector. Under "My Projects", click run
selector, select the shit you want, then click "cart download".

## 3. Configure prefetch (sratoolkit)
run `vdb-config -i`, then load the key you downloaded in 2. Change the path of the project. More
info [there](https://trace.ncbi.nlm.nih.gov/Traces/sra/sra.cgi?view=toolkit_doc&f=std). 

## 4. CD into the folder configured before and download
run the prefetch command **there**. If you wanna use aspera, use the -t and -a options and RTFM.
