# lambda

* Higher Order Functions

A higher order function (HOF) is a function that manipulates other functions by taking in functions as arguments, returning a function, or both. For example, the function compose below takes in two functions as arguments and returns a function that is the composition of the two arguments.

```python
def composer(func1, func2):
    """Return a function f, such that f(x) = func1(func2(x))."""
    def f(x):
        return func1(func2(x))
    return f
```

* currying

One important application of HOFs is converting a function that takes multiple arguments into a chain of functions that each take a single argument. This is known as currying. For example, the function below converts the pow function into its curried form:

```python

def curried_pow(x):
    def h(y):
        return pow(x, y)
    return h
curried_pow(2)(3)
8
```

* lambda

A lambda expression evaluates to a function, called a lambda function. For example, lambda y: x + y is a lambda expression, and can be read as "a function that takes in one parameter y and returns x + y."

A lambda expression by itself evaluates to a function but does not bind it to a name. Also note that the return expression of this function is not evaluated until the lambda is called. This is similar to how defining a new function using a def statement does not execute the function’s body until it is later called.

Unlike def statements, lambda expressions can be used as an operator or an operand to a call expression. This is because they are simply one-line expressions that evaluate to functions. In the example below, (lambda y: y + 5) is the operator and 4 is the operand.

```python

def f1():
    """
    >>> f1()
    3
    """
    "*** YOUR CODE HERE ***"
    return 3 

def f2():
    """
    >>> f2()()
    3
    """
    "*** YOUR CODE HERE ***"
    return lambda : 3

def f3():
    """
    >>> f3()(3)
    3
    """
    "*** YOUR CODE HERE ***"
    return lambda x : 3

def f4():
    """
    >>> f4()()(3)()
    3
    """
    "*** YOUR CODE HERE ***"
    return lambda : lambda x: lambda :3
    ```
