# add-data-frame-column

Repo for this article.
* code
* dataset

## Summary

* Problem- Add a column on `DataFrame` without errors
* Dataset
* Instruction - Columns must have same length of the `DataFrame`

## Problem

If you are confused of adding columns in `DataFrame`, always think to **Make a list**

This list needs to have same length as the `DataFrame`, and if you want to refer to an existed column for a new colullmn, be noticed what functions work with `pd.Series`

## Dataset

Data dictionary

|column|type|description|
|-|-|-|
|num|int|numbers between 0 and 99|
|let|str|alphabets|

## Instruction

Make a list which has same length of the `DataFrame`.

One thing you always have to notice when you add a column on `DataFrame` is that the column must have same length of the data set.

### Succeed

* `practice['a'] = ['a'+l for l in practice['let']]`
* `practice['high'] = ['high' if num > 50 else 'low' for num in practice['num']]`
* `practice['cap'] = [l.upper() for l in practice['let']]`

### Fail

* `practice['high'] = ['high' for num in practice['num'] if num > 50]`
  * This list length is different from `practice`'s
* `practice['cap'] = practice['let'].upper()`
  * `.upper()` does not work with `pd.Series`
