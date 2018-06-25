Creat Numpy arrays
===================
1.converting from a list
----------------------
```python
my_list = [1,2,3,4]
my_array1 = np.array(my_list)
my_array1
```
array([1, 2, 3, 4])

2.create a multi-dimensional array
-----------------------------------
```python
my_array = np.array([[1,2,3],[2,3,4]])
my_array
```
array([[1, 2, 3],  
>>[2, 3, 4]])
       
3.the size of the array
-------------------------------
```python
my_array.shape
```
(2L,3L)

4.the data type of the array
-------------------------------
```python
my_array.dtype
```
dtype('int32')

5.special case array
-------------------------------
Docstring:  
zeros(shape, dtype=float, order='C')  
Return a new array of given shape and type, filled with zeros.  
```python
np.zeros(5)
```
array([0., 0., 0., 0., 0.])  
注意这里的`0.` array里存储的数据类型是float, dtype('float64')
____________________________
Signature: np.ones(shape, dtype=None, order='C')  
Docstring:  
Return a new array of given shape and type, filled with ones.  
```python
np.ones([5,2])
```
array([[1., 1.],
>>[1., 1.],  
>>[1., 1.],  
>>[1., 1.],  
>>[1., 1.]])  
____________________________
empty(shape, dtype=float, order='C')  
Return a new array of given shape and type, without initializing entries.  
```python
np.empty([5,1])
```
array([[1.],  
>>[1.],  
>>[1.],  
>>[1.],  
>>[1.]])  
____________________________
Identity array  
Signature: np.eye(N, M=None, k=0, dtype=<type 'float'>, order='C')  
Docstring:  
Return a 2-D array with ones on the diagonal and zeros elsewhere.  
```python
np.eye(5)
```
array([[1., 0., 0., 0., 0.],  
>>[0., 1., 0., 0., 0.],  
>>[0., 0., 1., 0., 0.],  
>>[0., 0., 0., 1., 0.],  
>>[0., 0., 0., 0., 1.]])  
____________________________
using a range  
Docstring:  
arange([start,] stop[, step,], dtype=None)  
Return evenly spaced values within a given interval.  
```python
np.arange(0,50,2)
```
array([ 0,  2,  4,  6,  8, 10, 12, 14, 16, 18, 20, 22, 24, 26, 28, 30, 32, 34, 36, 38, 40, 42, 44, 46, 48])  

    
    
    
    
