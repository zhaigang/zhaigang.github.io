# Decorators
## It use from resolve which problem
assuming we work in that scenario like that:
Such as we have some function has writen finished , and it's run well on-line, we want to add a feature to statistic how those function runtime , and write those information to log. we have two choose, the one is we add code to the function, other way we consider that does have one way not broken the exists code and add this feature.
Otherwise, if we want to add some step before the function execute, such as we have a some function we consume remote resource , and remote require ours could call the interface over 3 times in one minutes. we want to add a flow control to our function. we want to control which check should before the function and after.

# Test it step by step

# what happened when we add a decorator before function

```python
import random
import time

def my_decorator(*args, **kwargs):
    print('args', args)
    print('kwargs', kwargs)
    # return args[0] # there must return a executable function,otherwise this error occur error.

@my_decorator
def function1_basic():
    print('execute function')
    time.sleep(random.randint(3, 4))
    return True, 'Bussinse run success'

function1_basic()
""" output
args (<function function1_basic at 0x7f5df1b362a0>,)
kwargs {}
Traceback (most recent call last):
  File "/mnt/e/workspace/python_revise/src/test16_decorator/basic2_func.py", line 15, in <module>
    function1_basic()
TypeError: 'NoneType' object is not callable

"""
```
though this sample we can get some conclusion:
1. decorator function must return an executable function(that's is why we see the decorator function looks have many layers usually.).
2. if we don't add the parenthesis when we call the decorator, it will give function address to the decorator.

### three layers of decorators
we often see the decorators has the parameter, let's we discover how it run.

```python
import random
import time

def my_decorator(*decorator_args, **decorator_kwargs):
    def wrapper(*wrapper_args, **wrapper_kwargs):
        def function(*function_args, **function_kwargs):
            print('function_args', function_args)
            print('function_kwargs', function_kwargs)
            wrapper_args[0](*function_args, **function_kwargs)
        print("wrapper_args", wrapper_args)
        print("wrapper_kwargs", wrapper_kwargs)
        return function
    print('decorator_args', decorator_args)
    print('decorator_kwargs', decorator_kwargs)
    return wrapper

@my_decorator(5)
def function1_basic(bussiness_type):
    print('execute function:%s' % bussiness_type)
    time.sleep(random.randint(3, 4))
    return True, 'Bussinse run success'

function1_basic('create cloud server')
"""
decorator_args (5,)
decorator_kwargs {}
wrapper_args (<function function1_basic at 0x7ff22484a660>,)
wrapper_kwargs {}
function_args ('create cloud server',)
function_kwargs {}
execute function:create cloud server
"""
```
through this sample we can get some conclusion:
1. three lays from out lay to inner lay is use to accept decorator argument, function object, function argument respectively.

### test use the three laiers on a class
```python

def my_decorator(*decorator_args, **decorator_kwargs):
    def wrapper(*wrapper_args, **wrapper_kwargs):
        def function(*function_args, **function_kwargs):
            print('function_args', function_args)
            print('function_kwargs', function_kwargs)
            return wrapper_args[0](*function_args, **function_kwargs)
        print("wrapper_args", wrapper_args)
        print("wrapper_kwargs", wrapper_kwargs)
        return function
    print('decorator_args', decorator_args)
    print('decorator_kwargs', decorator_kwargs)
    return wrapper

@my_decorator(5)
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def run(self):
        print('my name is %s, my age is :%s' % (self.name, self.age))

obj = Person('Tom', 18)
obj.run()
""" output
decorator_args (5,)
decorator_kwargs {}
wrapper_args (<class '__main__.Person'>,)
wrapper_kwargs {}
function_args ('Tom', 18)
function_kwargs {}
my name is Tom, my age is :18
"""
```
through this test, we can discover the class decorator behave like the function decorator, not have difference.

### if our decorator logic was complex
```python

class MyDecorator:
    def __init__(*decorator_args, **decorator_kwargs):

        print('decorator_args', decorator_args)
        print('decorator_kwargs', decorator_kwargs)

    def __call__(self, *call_args, **call_kwargs):

        def wrapper(*wrapper_args, **wrapper_kwargs):
            print('wrapper args', wrapper_args)
            print('wrapper kwargs', wrapper_kwargs)
            call_args[0](*wrapper_args, **wrapper_kwargs)
        print('call_args', call_args)
        print('call_kwargs', call_kwargs)
        return wrapper
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    @MyDecorator(5)
    def run(self, kilometers):
        print('my name is %s, my age is :%s, today i will run %s kilometers' % (self.name, self.age, kilometers))

obj = Person('Tom', 18)
obj.run(8)

```
summarize:
1. tow function of \_\_init\_\_ and \_\_call\_\_ is Required, because init function is use for receive the decorator argument, and call function use for define which step we should do before execute the decorated function.

### decorators maybe change your function

```python
from functools import wraps

def my_decorator(func):
    """this doc is for my_decorator"""
    @wraps(func) # use wraps to keep function doc and name
    def wrapper(*args, **kwargs):
        """this doc is for wrapper"""
        print("before run...")
        return func(*args, **kwargs)
    return wrapper

@my_decorator
def original_function(a, b):
    """this doc is for original_function"""
    return a + b

# 运行结果：
print(original_function.__name__) # if we not add the wraps to the wrapper, the output will be wrapper
print(original_function.__doc__)  # if we not add the wraps to the wrapper, the output will be this doc is for wrapper
```