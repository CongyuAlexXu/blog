Series
================================
  What is Series? (It's an array of data and data labels, its index)  
  
1. Create a  Series
------------------------
```python
import numpy as np
from pandas import Series, DataFrame
import pandas as pd 

obj = Series([1,5,2,8,9])
obj
```
0    1  
1    5  
2    2  
3    8  
4    9  
dtype: int64  

2. Show the values and index of Series.
----------------------------------
```python
obj.values
obj.index # 不要写一起
```
array([1, 5, 2, 8, 9], dtype=int64)  
RangeIndex(start=0, stop=5, step=1) (这是**_最新版的pandas表示index的方法_**，简洁，但个人认为没有以前直观)

3.Create a series with index
--------------------------------
Let's create a series called 'NBA all-time scoring leaders - total number of points scored** (as of April 11th, 2018)' 
```python
nba_score_leader = Series([38387,36928,33643,32292], index=['Kareem Abdul-Jabbar','Karl Malone','Kobe Bryant','Michael Jordan'])
nba_score_leader
```
Kareem Abdul-Jabbar    38387  
Karl Malone            36928  
Kobe Bryant            33643  
Michael Jordan         32292  
dtype: int64  

4. Other operation of this Series
--------------------------------------
Using index to select Series value
```python
nba_score_leader['Kobe Bryant']
```
33643 
Checking with array operation. For instance: check any player has the score > 33000
```python
nba_score_leader[nba_score_leader > 33000]
```
Kareem Abdul-Jabbar    38387  
Karl Malone            36928  
Kobe Bryant            33643  
dtype: int64  

Treating Series as an ordered dictionary  For instance: check if the Lebron James in Series  
```python
'Lebron James' in nba_score_leader
```
False  

Converting Series into Python dictionary
```python
nsl_dic = nba_score_leader.to_dict()
nsl_dic
```
{'Kareem Abdul-Jabbar': 38387L,  
 'Karl Malone': 36928L,  
 'Kobe Bryant': 33643L,  
 'Michael Jordan': 32292L}  
 
 Converting dictionary back to Series
 ```python
 nsl_Series = Series(nsl_dic)
 nsl_Series
 ```
Kareem Abdul-Jabbar    38387  
Karl Malone            36928  
Kobe Bryant            33643  
Michael Jordan         32292  
dtype: int64  

5.Passing a dictionary the index will have the dict key in order
---------------------------------------------------------------------
```python
player=['Kareem Abdul-Jabbar','Karl Malone','Kobe Bryant','Michael Jordan','Lebron James','James Harden']
# Let's redefine a Series
obj2 = Series(nba_score_leader, index = player)
obj2
```
Kareem Abdul-Jabbar    38387.0  
Karl Malone            36928.0  
Kobe Bryant            33643.0  
Michael Jordan         32292.0  
Lebron James               <font color='red'>NaN</font>  
James Harden               NaN  # the value of null can be shown
dtype: float64   

using isnull and notnull to find missing data
```python
pd.isnull(obj2)
```
Kareem Abdul-Jabbar    False  
Karl Malone            False  
Kobe Bryant            False  
Michael Jordan         False  
Lebron James            True  
James Harden            True  
dtype: bool   

Or using notnull to find missing data
```python
pd.notnull(obj2)
```
Kareem Abdul-Jabbar     True  
Karl Malone             True  
Kobe Bryant             True  
Michael Jordan          True  
Lebron James           False  
James Harden           False  
dtype: bool   

6. Pandas can add automatically aligns data by index
---------------------------------------------------
```python
nba_score_leader + obj2
```
James Harden &nbsp;&nbsp;&nbsp;NaN  
Kareem Abdul-Jabbar    76774.0  
Karl Malone            73856.0  
Kobe Bryant            67286.0  
Lebron James               NaN  
Michael Jordan         64584.0  
dtype: float64  
    we can see that NaN is still  NaN, but other values doubles
    
7. Give a series name
```python
obj2.name = 'NBA all-time scoring leaders'
obj2
```
Kareem Abdul-Jabbar    38387.0  
Karl Malone            36928.0  
Kobe Bryant            33643.0  
Michael Jordan         32292.0  
Lebron James               NaN  
James Harden               NaN  
Name: NBA all-time scoring leaders, dtype: float64

8 Give a name to index
```python
obj2.index.name = 'All Stars'
obj2
```
All Stars
Kareem Abdul-Jabbar    38387.0  
Karl Malone            36928.0  
Kobe Bryant            33643.0  
Michael Jordan         32292.0  
Lebron James               NaN  
James Harden               NaN  
Name: NBA all-time scoring leaders, dtype: float64
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
