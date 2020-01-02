# Python Tricks Part 2

In this Python Tricks we will focus on the useful features & formatting styles which we avoid to use but these feature deserves
more attention. Here we will see some tricks which make your program more reliable.
Lets start with 

## Assert in Python : 

Assert is a debugging aid which test condition. If given condition is true your code run as normal but if condition is false,
an AssertionError exception will raised.

For Eg:

Below Example shows how assert will speedup your debugging effort. *appy_dis(pro, dis)* function taking product & 
discount on product. If discount is more than 0 & less than price of product then code will run without any error but
if discount will be more than price AssertionError will raise. 


```python
>>> def appy_dis(pro, dis):
...     price  = int(pro['price']*(1.0 * dis))
...     assert 0<= price <= pro['price']  # Assert Statement
...     return price
... 
>>> shoes = {'name': 'Sport Shoe' , 'price':2400}
>>> appy_dis(shoes, 0.5) # Run Successful
1200
>>> appy_dis(shoes, 2) # Discount increase product price
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "<stdin>", line 3, in appy_dis
AssertionError
```

## Underscores in Python:

Underscores(single or double)have a meaning in python variable & Method names.

lets check how single & double underscore will change the behaviour of your Python code.

- Single Leading Underscore : _var

This won't effect any code but Underscore prefix is meant as hint to tell another programmer that a variable/method started 
with single underscore is intended for internal use only.

***Note*** for more details read *PEP8* : "Style Guide for Python Code"

For Eg:

```Python
>>> class test:
...     def __init__(self):
...             self.foo = 11
...             self._bar = 23
... 
>>> t = test()
>>> t.foo
11
>>> t._bar
23
```
