---
title: "How to - Pandas"
weight: 2
resources:
params:
date: 2022-12-19T18:00:53-05:00
showDate: false
draft: false
tags: ["blog","howto"]
---

```python
import pandas as pd

fh = "/path/to/file.csv"

## Reading csv file
df = pd.read_csv(fh)

df = pd.read_csv(fh,header=None)

df = pd.read_csv(fh,header=None,sep='\s+',engine=python,index_col=False)

df = pd.read_csv(fh,header=None,sep='\s+',engine=python,index_col=False, names=['name','id','start','end'])

## Working with NaN

# Drop all rows with NaN value in a dataframe
df.dropna()
df[df.notnull().all(1)]

#axis=0:row, axis=1:column, subset
df.dropna(how='all',axis=0)
df.dropna(subset=["name","id"]

#Dropping NaN rows specific column
df[df['start'].notna()]
```
