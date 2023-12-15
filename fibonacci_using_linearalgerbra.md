# fibonacci :an apilcation of linaear agerbra

```python
def fib_iter(a,b,p,q,count):
   if(count == 0):
      return b
   if(count%2 == 0):
      q_ = q*q+2*p*q
      p_ = p*p+q*q
      count_ = count//2
      return fib_iter(a,b,p_,q_,count_)
   else:
      a_ = b*q+a*q+a*p
      b_ = b*p+a*q
      count_ = count - 1
      return fib_iter(a_,b_,p,q,count_)
def fib(n):
   return fib_iter(1,0,0,1,n)
for i in range (0,10):
   print(fib(i))
```
