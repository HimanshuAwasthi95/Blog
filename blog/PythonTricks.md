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

- **Single Leading Underscore : _var**

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

- **Single Trailing Underscore : var_**

Mostly trailing underscore use for bestfit naming convention of *variable name* or also we can't use class, def & so many as variable name so we can use underscore for breaking this naming conflict.

For Eg:

```python
>>> def class_student(x,y):
...     # body
...     return true
... 
>>> def class(x,y):
  File "<stdin>", line 1
    def class(x,y):
            ^
SyntaxError: invalid syntax
>>> def class_student(x,class):
  File "<stdin>", line 1
    def class_student(x,class):
                            ^
SyntaxError: invalid syntax
>>> def class_student(x,class_):
...     pass
...     return true
... 
>>> 
```

- **Double Leading Underscore : __var**

So from here underscore become magical because till now it is basically shows naming conventions only. Double leading underscore force python interpreter to rewrite the attribute name in order to avoide naming conflicts in subclasses.

This is called **Name Mangling**.

For Eg:

```python
>>> class test:
...     def __init__(self):
...             self.foo = 11
...             self.__bar = 23
... 
>>> t = test()
>>> t.foo
11
>>> t.__bar
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'test' object has no attribute '__bar'
```
from above example we can see that test doesn't have __bar .

lets check what all contains by object of Test Class.

```python
>>> dir(t)
['__class__', '__delattr__', '__dict__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__le__', '__lt__', '__module__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', '__weakref__', '_test__bar', 'foo']
```
So **__bar** is not available here but if you notice carefully you find ***_test__bar*** in this object. This is the name mangling which *Python Interpreter* applies. This protect variable to getting overridden in subclass.

lets try to access this *__bar* :

```python
>>> t._test__bar
23
```

Bang Bang ! This is <3 

- **Double leading & trailing Underscore : __var__**

This one is my favorite because variable which start & end with double underscore are reserved for special use in the language and also the are 100% secure from *Python Interpretor*(Means no change done by Python Interpreter).

For Eg:

```python
>>> class DoubleUnderscore:
...     def __init__(self):
...             self.__dotest__ = 42
...
>>> DoubleUnderscore().__dotest__
42
```

So for basic naming convention better to avoid this Double Leading & Trailing underscore because we all know this rule covers most intresting feature & thing like __init__ for object constructors, __call__ to make objects callable or so many others.

- **Single Underscore : _ **

Single Underscore nothing but a valid Variable name which shows variable is temporary or insignificant.

let take a basic example : 

```python
>>> _ = 5
>>> _
5
```

Sometimes we don't need to access index of our loops in that case also we can use ***" _ "*** .

For Eg:

```python
>>> for _ in range(5):
...     print("hello ! World")
... 
hello ! World
hello ! World
hello ! World
hello ! World
hello ! World
```

Apart from use as temporary variable we can use this " _ " to get the result of the last expression in Python REPL session. 

```python
>>> 20+3
23
>>> 45+2
47
>>> _
47
```

## String Formatting in Python:

String formatting is one of the useful feature of python language.












