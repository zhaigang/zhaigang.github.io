# Singleton pattern

[code path](https://github.com/zhaigang/pythonRevise/tree/main/src/test15_singleton_pattern)

## 1. Why we need it

```python
class ClassName:
    def __init__(self):
        pass
obj1 = ClassName()
obj2 = ClassName()
```

It will generate many instance class, if this class control some limited resource, such as database connection, or  we load many local configuration and dont want repeat load it . That's why we need the Singleton pattern.

## 2. how to implement it

### 2.1 nature implement in Python.

Such as we define a variable in file a like this.

```python
var_a = list()
```

when we import it in file b and c, like this.

```python
from a import var_a
print('the caller is file_a and the instance id is %s' % id(var_a))
```

we can test call it in file d

```python
import b
import d
```

then we can see the result as this

```python
ggg@DESKTOP-FTDT2HN:/mnt/e/workspace/python_revise/test15_singleton_pattern/basic$ python3 d.py
the caller is file_b and the instance id is 139693675836480
the caller is file_c and the instance id is 139693675836480
```

throgh this test we can prove __the class instance we only  instantiate once when we import it in some difference place__

### 2.2 How the instantiate motion run.

1. we write a scpoe of code to test

```python
   class MyClass:
       class_var = None
       # custom define __new__，observe how to create
       def __new__(cls, *args, **kwargs):
           print(f"1. __new__ called, create {cls.__name__} instance")
           # call father class __new__function and retruen a instance 
           instance = super().__new__(cls)
           return instance

       # __init__ will run after __new__ return the class instance
       def __init__(self, name):
           print(f"2. __init__ called, and class_var id is :%s" % id(MyClass.class_var))
           self.name = name
# instantiation
obj = MyClass("test")
obj2 = MyClass("test2")
```

2. the result like this
   
   ```python
   ggg@DESKTOP-FTDT2HN:/mnt/e/workspace/python_revise/test15_singleton_pattern$ python3 test_class1.py 
   1. __new__ called, create MyClass instance
   2. __init__ called, and class_var id is :10746016
   1. __new__ called, create MyClass instance
   2. __init__ called, and class_var id is :10746016
   ```

3. We have drawn a conclusion throgh testing.
   
   1. when we instantiation the class, the Python will run \_\_new\_\_ at first, to generate the instance, after run \_\_init\_\_ to initalize this class. 
   2. The class variable will only generate once, whatever we instatiate how many times.

### 2.3 Use class variable to implement the signleton partten.

1. we want to add the two class variable to control the initialize flow, use the class_instance to record the singleton instance, and use the `initialized` to record does this class inital finished.
   
   ```python
   class MyClass:
       class_instance = None
       initialized = False
       def __new__(cls, *args, **kwargs):
           if MyClass.class_instance is None:
               print(f"1. __new__ called, create {cls.__name__} instance")
               MyClass.class_instance = super().__new__(cls)
           else:
               print('dont need instantiate class')
           return MyClass.class_instance
   
       # __init__ will run after __new__ return the class instance
       def __init__(self, name):
           if MyClass.initialized is False:
               print(f"2. __init__ called, and this class id is :%s" % id(self))
               self.name = name
               MyClass.initialized = True
           else:
               print("dont need init it.")
   
   # instantiation
   obj = MyClass("test")
   obj2 = MyClass("test2")
   ```

2. let's we run it.
   
   ```python
   ggg@DESKTOP-FTDT2HN:/mnt/e/workspace/python_revise/test15_singleton_pattern$ python3 test_class2.py 
   1. __new__ called, create MyClass instance
   2. __init__ called, and this class id is :140149019777728
   dont need instantiate class
   dont need init it.
   ```
   
   > though this code we can simplely to implement the singleton pattern, but if  the init function will run a long time, or run it in High-concurrency scenarios, it may be occur some proble, so we should add the threading lock on it.

### 2.4 the  High-concurrency scenarios.

```python
import threading

class MyClass:
    class_instance = None
    initialized = False
    def __new__(cls, *args, **kwargs):
        if MyClass.class_instance is None:
            with threading.Lock():
                if MyClass.class_instance is None:
                    print(f"1. __new__ called, create {cls.__name__} instance")
                    MyClass.class_instance = super().__new__(cls)
        return MyClass.class_instance

    # __init__ will run after __new__ return the class instance
    def __init__(self, name):
        if MyClass.initialized is False:
            with threading.Lock():
                if MyClass.initialized is False:
                    print(f"2. __init__ called, and this class id is :%s" % id(self))
                    self.name = name
                    MyClass.initialized = True

# instantiation
obj = MyClass("test")
obj2 = MyClass("test2")
```

## 3. other way to implement it.

1. code

```python
def singleton(cls):  
    instances = {}  # 缓存所有单例类的实例  
    def wrapper(*args, **kwargs):  
        if cls not in instances:  
            instances[cls] = cls(*args, **kwargs)  
        return instances[cls]  
    return wrapper

@singleton
class MyClass:
    # __init__ will run after __new__ return the class instance
    def __init__(self, name):
        print(f"2. __init__ called, and this class id is :%s" % id(self))

# instantiation
obj = MyClass("test")
obj2 = MyClass("test2")
```

2. run result

```python
ggg@DESKTOP-FTDT2HN:/mnt/e/workspace/python_revise/test15_singleton_pattern$ python3 test_class4_decroter.py
2. __init__ called, and this class id is :139917632559232
```
