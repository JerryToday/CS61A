# recursion

A recursive function is a function that is defined in terms of itself.There are three main steps in a recursive definition:

```python
def factorial(n):
    """Return the factorial of N, a positive integer."""
    if n == 1:
        return 1
    else:
        return n * factorial(n - 1)
```

* Base case. You can think of the base case as the case of the simplest function input, or as the stopping condition for the recursion.In our example, factorial(1) is our base case for the factorial function.

* Recursive call on a smaller problem. You can think of this step as calling the function on a smaller problem that our current problem depends on. We assume that a recursive call on this smaller problem will give us the expected result; we call this idea the "recursive leap of faith".In our example, factorial(n) depends on the smaller problem of factorial(n-1).

* Solve the larger problem. In step 2, we found the result of a smaller problem. We want to now use that result to figure out what the result of our current problem should be, which is what we want to return from our current function call.In our example, we can compute factorial(n) by multiplying the result of our smaller problem factorial(n-1) (which represents (n-1)!) by n (the reasoning being that n! = n * (n-1)!).

```python
def multiply(m, n):
    """ Takes two positive integers and returns their product using recursion.
    >>> multiply(5, 3)
    15
    """
    if(n==1):return m
    else:
        return m + multiply(m,n-1)
```

* Write a recursive version of hailstone in hw01

```python
def hailstone(n):
    """Print out the hailstone sequence starting at n, and return the number of elements in the sequence.
    >>> a = hailstone(10)
    10
    5
    16
    8
    4
    2
    1
    >>> a
    7
    >>> b = hailstone(1)
    1
    >>> b
    1
    """
    "*** YOUR CODE HERE ***"
    print(n)
    if (n == 1): return 1 
    if(n%2==0):
        return 1+hailstone(n//2)
    else:
        return 1+hailstone(3*n+1)
```
