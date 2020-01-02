# New Features of Python 3.8

Hey Everyone,
Finally I switched to more advance & modern code-base of Python Language which is Python 3.8. Python 3.8 was released on October 14th, 2019. We all know Python is one of the widely used language which can be used for Automation, Machine Learning, Web Development  etc.
Being a Linux user I never feel to update or change version of Python or other application because every update of Linux come up with proper stable version of most of the application specially Python & GCC.

So Why I switched to Python 3.8 ?

Because I read the official documentation of Python 3.8 & believe me I can't stop my self to use these features.
Python 3.8 is introduced you some beautiful new syntax, memory sharing, more efficient serialization and de-serialization, new Modules, improved modules, and a lot of cool changes & add-ons.

Lets begin with what’s new in Python 3.8 :
1.  Assignment Expressions :
Most visible & interesting change of Python 3.8 is this Assignment Expression ( :=) change, and affectionately known as “the walrus operator”
Eg :

// Python 3.8 Example
>>> a = [5,6,7,7,8,8,8]
>>> if(n := len(a))< 10 :
...     print(f"Length of a is {n}")
... 
Length of a is 7

Currently, this feature is available only in statement form but may be in future we are able to see best use of  this expression within comprehensions, such as list comprehensions, and lambda functions also It will give power debugging without code refactoring.
Try to limit use of the walrus operator to clean cases that reduce complexity and improve readability.(Special Note from Official Docs)

2. Positional-only parameters :
This is new parameter syntax for function definition which allow developer to create argument positional only. So now we can understand which argument is positional & which one is keyword argument.
The / separates positional from keyword arguments.
For Eg:

>>> def f(a,b,/,c,d,*,e,f):
...     print(a,b,c,d,e,f)
... 
>>> f(10, 20, 30, d=40, e=50, f=60) //Valid Call of Function
10 20 30 40 50 60
>>> f(10,20,30,40,50,f=60)
TypeError: f() takes 4 positional arguments but 5 positional arguments (and 1 keyword-only argument) 
were given

In the above example parameters a and b are positional-only, while c or d can be positional or keyword, and e or f are required to be keywords

3. f-strings support = for self-documenting expressions and debugging:
f-string or formatted string literals added an = specifier such as f'{expr=}' which allow us to print text and computed values in same expression.
For Eg:

>>> import datetime
>>> date = datetime.date(1991, 10, 12)
>>> f'{date = } was on a {date:%A}'
'date = datetime.date(1991, 10, 12) was on a Saturday'
>>> user = 'himanshu'
>>> age = 24
>>> f'{user=} is of {age =}'
"user='himanshu' is of age =24"


4. Constructors of int, float and complex will now use the __index__() special method, if available and the corresponding method __int__(), __float__() or __complex__() is not available.

5. Added support of \N{name} escapes in regular expressions:

>>> notice = 'Copyright © 2019'
>>> copyright_year_pattern = re.compile(r'\N{copyright sign}\s*(\d{4})')
>>> int(copyright_year_pattern.search(notice).group(1))
2019


6. Dict and dictviews are now iterable in reversed insertion order using reversed().

7. Generalized iterable unpacking in yield and return statements no longer requires enclosing parentheses. This brings the yield and return syntax into better agreement with normal assignment syntax:

>>> def parse(family):
...     lastname, *members = family.split()
...     return lastname.upper(), *members
... 
>>> parse('himanshu akash rahul andy kumar')
('HIMANSHU', 'akash', 'rahul', 'andy', 'kumar')

8. New Modules :
The new importlib.metadata module provides (provisional) support for reading metadata from third-party packages. For example, it can extract an installed package’s version number, list of entry points, and more:

>>> # Note following example requires that the popular "requests"
>>> # package has been installed.
>>>
>>> from importlib.metadata import version, requires, files
>>> version('requests')
'2.22.0'
>>> list(requires('requests'))
['chardet (<3.1.0,>=3.0.2)']
>>> list(files('requests'))[:5]
[PackagePath('requests-2.22.0.dist-info/INSTALLER'),
 PackagePath('requests-2.22.0.dist-info/LICENSE'),
 PackagePath('requests-2.22.0.dist-info/METADATA'),
 PackagePath('requests-2.22.0.dist-info/RECORD'),
 PackagePath('requests-2.22.0.dist-info/WHEEL')]

Apart from these a lot of useful updates & changes in this Python 3.8 which improving performance and also helps to write more clean , readable code.
For complete Description visit ​official documentation.
I used this official docs as a reference for this blog.

Happy Coding
