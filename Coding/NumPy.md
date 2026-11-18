Tags:
- #coding
- #Python-libraries

In this fil, I will report all the main notes on functions used in NumPy. 

##### random.randn(dim1, dim2, ...)
It return the sample from the "standard normal" distribution. It is called as `np.random.randn(d0, d1...)` where the arguments are the dimensions of the sample computed. 

##### .full(dimensions, value)
It creates an array given the tuple dimension `dimensions` and it inserts the value `value` in it. 

##### .shape
Provide the shape of the array from which the function is called form. 
##### .size
Provides the number of points of the entire array, including all dimensions.

##### .column_stack()

Given multiple 2D arrays, you cans tack them horizontally using np.column_stack(arr1, arr2)