# Python Fire : Automatically Turn Your Code In To CLI
**Python Fire** is an Opensource library created by Google which automatically generates command line interface from any python object. It give power of developing and debugging any Python Code. 

**Lets start with Python Fire**

## Installation

### Using Pip:
> pip install fire

### Using Conda:
> conda install fire -c conda-forge

### or , clone the source & run :
> python setup.py install

## Test a simple example
```
import fire

class calc(object):
	
	def square(self, number):
		return number**2

if __name__ == '__main__':
	fire.Fire(calc)

```
Open Your Terminal & Run,

> python calc.py square 4 # 16 
