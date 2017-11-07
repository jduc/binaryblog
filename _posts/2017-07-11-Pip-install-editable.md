---
layout: default
title:  "Pip install editable"
categories: python
description: "How to make editable install for python pip"
---

# Pip: editable install

When devlopping a python package, it's annoying to have to install it after
each change. Hopefully, it's possible to install the python package in editable
mode, which allows the code to be changed and instantly available as if it was
installed.

* Simply: `pip install -e package`

Of course, you'll have to compile whatever external library is needed with 
`python setupt.py build_ext --inplace` prior to install.
