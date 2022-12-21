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

# Displaying complete dataframe
pd.set_option("display.max_rows", None, "display.max_columns", None)
#pd.set_option('display.max_colwidth', None)  
pd.set_option('display.max_colwidth', 199)  
pd.set_option('display.height',1000)
pd.set_option('display.max_rows',500)
pd.set_option('display.max_columns',500)
pd.set_option('display.width',1000)
pd.set_option('display.max_columns', None)  # or 1000
pd.set_option('display.max_rows', None)  # or 1000
#pd.set_option('display.max_colwidth', None)  # or 199
pd.set_option('display.max_colwidth', -1)


fh = "/path/to/file.csv"

## Reading csv file
df = pd.read_csv(fh)

df = pd.read_csv(fh,header=None)

df = pd.read_csv(fh,header=None,sep='\s+',engine=python,index_col=False)

df = pd.read_csv(fh,header=None,sep='\s+',engine=python,index_col=False, names=['name','id','start','end'])


## Working with index
df.set_index('name',inplace=True)
df.set_index('name',drop=False)

df.reset_index()
df.reset_index(drop=True)
# Searching becomes easy with indexing
df.loc[50]

## High level info and stats
df.info()

#rows and columsn
df.shape

#number of elements
df.size

#number of rows
len(df)

#include, exclude - object, float
df.describe()

## Working with NaN

# Drop all rows with NaN value in a dataframe
df.dropna()
df[df.notnull().all(1)]

#axis=0:row, axis=1:column, subset
df.dropna(how='all',axis=0)
df.dropna(subset=["name","id"])

#Dropping NaN rows specific column
df[df['start'].notna()]

## Combining dataframes
# Default value of ignore_index is False
df3 = df1.append(df2,ignore_index=True)

# Inserting column
df = df.assign(new_col_name=[3,7,4])
df = df.insert(3,'new_col_name',[3,7,4])

# Lambda 
#lambda x: x.points / 2

## String operations

## Comprehensions for performing multiple string operations



## Groupby
#Printing grouped df
df.groupby('A').apply(print)
df.groupby(by).apply(lambda a: a[:])
df.groupby(by).apply(lambda a: a.drop(by, axis=1)[:])


(df.groupby("Groups", as_index=False)
           .agg({"Date":"first", "data1":"sum", "data2":"sum"}))
Out[5]:

```
