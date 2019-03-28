---
layout: post
title: "Python Class (1)"
description: "Class and Instance"
date: 2019-03-25
tags: [Python, Class, Instance]
category: Python
comments: true
share: true
---

## Class & Instance


> - attributes & methods are inside of the class
> - A method is a function that “belongs to” an object
> - instance variable contains data that is unique to each instance
> - ```__init__```: when we create an object, it initializes the object as default.
> - ```__init__(self)```: each method in class automatically receives instance as the first argument (self)


### Basic Example
```python
a = 10  # local variable

class Test:
	b = 20  # class variable

print(a)
print(Test().b)
```

<pre class="output">
10
20 </pre>

<br>

```python
# creates a new instance of the class 'Test()' and assigns this object to the local variable t
t = Test()
# class variable is accessible only from class object
print(t.b)
t.b = 30
print(t.b)
```
<pre class="output">
20
30
</pre>

<br>

```python
t1 = Test()
t2 = Test()
# t1 and t2 are own unique instances of Test class with different locations in memory
print(t1)
print(t2)
```

<pre class="output">
<__main__.Test object at 0x0000000004FDA5F8>
<__main__.Test object at 0x0000000004FDA668>
</pre>

<br>

```python 
# setting attribute b that are unique to each instance
t1.b = 10
t2.b = 20
print(t1.b, t2.b)
```
<pre class="output">
10
20 </pre>

<br>

### Person Example
Create an instance called obj from Person class. Then, set the attributes of this instance manually.
```python
class Person:
    name = str()
    age = int()
    salary = float()

obj = Person()  # create an instance
obj.name = 'kimmy'  # set attributes
obj.age = 30
obj.salary = 1000.0
print('name: ',obj.name, ', age: ', obj.age, ', salary: ', obj.salary)
```
<pre class="output">
name:  kimmy , age:  30 , salary:  1000.0 </pre>

<br>

In this example, create an instance called obj1 from Person1 class and set the attributes of this instance at once by creating a method called 'setItem()'. Furthermore, I've created another method called printInfo() to print the information.

```python
class Person1:
    name = str()
    age = int()
    salary = float()

    #method (not function)
    def setItem(self, name, age, salary):  # self is instance
        self.name = name
        self.age = age
        self.salary = salary

    # instance is the only argument that we'll need in this method
    def printInfo(self):  # don't forget to put self
        print('name: {}, age: {}, salary: {}'.format(self.name, self.age, self.salary))


obj1 = Person1()
obj1.setItem('kimmy', 30, 10000)
obj1.printInfo()
```
<pre class="output">
name:  kimmy , age:  30 , salary:  1000.0
</pre>

<br>

In this example, create ```__init__``` method to directly initialize the instance variables.

> - in class Person1, we did not use init method. Therefore, we had to create an object and use setItem method to pass in the information of attributes.
> - in class Person2, we can create an object and pass in information of attributes in one line by creating ```__init__``` method.

```python
class Person2:
    name = str()
    age = int()
    salary = float()
    
    def __init__(self, name, age, salary): 
        self.name = name  #set instance variables
        self.age = age
        self.salary = salary

    def printInfo(self): 
        print('name: {}, age: {}, salary: {}'.format(self.name, self.age, self.salary))

# init method will run automatically
# obj2 will be passed in as self and it will set all these attributes
obj2 = Person2('Kimmy', 30, 10000) 

# these two have the same logic
obj2.printInfo() # automatically pass in self
Person2.printInfo(obj2) # calls method on the class and it doesnt know which instance. so pass in intance
```
<pre class="output">
name:  Kimmy , age:  30 , salary:  10000
name:  Kimmy , age:  30 , salary:  10000
</pre>