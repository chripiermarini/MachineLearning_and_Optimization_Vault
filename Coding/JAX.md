Tags:
- #machine-learning 
- #Python-libraries 

Main library for ML algorithms implementation and computation.

Topics below
# Arrays

Arrays in **JAX** are immutable objects. One can create an array through the *JAX.numpy* API, or maybe going even more lower level (better control is required) with the *JAX.lax* API. Operations through the [[NumPy]] API are quite similar to the normal [[NumPy]] library. 

One cannot modify an array, but it can create faster another one from an existing array through the `.at()` method. One can either select a specific element by providing the index of the element to modify, or even slicing a matrix by inputting a range. Still, as JAX is optimised for computation, JAX does not raise errors. 

E.g. the following code does not raise any errors:

```Python
import jax.numpy as jnp
x = jnp.array([1,2,4])

print(x[5]) ## it will print 4, as it is the last element of the array! 
## No out-of-bounds error.
```

# Transformations

Transformations in JAX are divided into three major groups: 

1) ***.grad()***, which computed the gradient of a function via automatic differentiation; 
2) ***.vmap()***, which 'vectorises' a function written for a single example into one that operates efficiently over batches via automatic vectorisation. 
3) ***.jit()***, which compiles a function to make it fast. This transformation does not involve any changes in the function itself, apart from performance (Just-in-time compilation).
### .grad()

It computes the derivative via automatic differentiation. By providing a numerical function to the `.grad()` method, it compute the derivative with respect to the first argument of the function by default. The derivative function is provided as output of the method.

One can compute the derivative with respect to different arguments using the `argnums` arg.

```Python
def sigmoid(x):
  return 0.5 * (jnp.tanh(x / 2) + 1)

# Outputs probability of a label being true.
def predict(W, b, inputs):
  return sigmoid(jnp.dot(inputs, W) + b)

# A toy dataset, and some parameter values.
inputs = jnp.array([[0.52, 1.12,  0.77],
                    [0.88, -1.08, 0.15],
                    [0.52, 0.06, -1.30],
                    [0.74, -2.49, 1.39]])
targets = jnp.array([True, True, False, True])
W = jnp.array([0.1, 0.4, -0.3])
b = 0.5

# Training loss is the negative log-likelihood of the training examples.
def loss(W, b):
  preds = predict(W, b, inputs)
  label_probs = preds * targets + (1 - preds) * (1 - targets)
  return -jnp.sum(jnp.log(label_probs))

# Differentiate `loss` with respect to the first positional argument:
W_grad = jax.grad(loss, argnums=0)(W, b)
print(f'{W_grad=}')

# Since argnums=0 is the default, this does the same thing:
W_grad = jax.grad(loss)(W, b)
print(f'{W_grad=}')

# But you can choose different values too, and drop the keyword:
b_grad = jax.grad(loss, 1)(W, b)
print(f'{b_grad=}')

# Including tuple values:
W_grad, b_grad = jax.grad(loss, (0, 1))(W, b)
print(f'{W_grad=}')
print(f'{b_grad=}')
```
### .vmap()

The above function transforms the function provided as input (which can compute only one element at a time) to a new function that can work efficiently on batches of inputs. 

For example, one can have the following function:

```python 
def parabolic_function(x):
	return x**2
```

And, in order to apply to an array of the type:

```Python
array = jnp.arange(5)
new_array = jnp.stack([array, array], axis = 1)
```
(remember here: ***stacks*** adds a new axis! Hence , as `array` is one dimensional, the result has shape (5,2). )

One can simply transform the new function as follows:
```Python
parallel_parabolic_function = jax.vmap(parabolic_function)
print(parallel_parabolic_function(new_array))
```


Check here `in_axes` and `out_axes`.