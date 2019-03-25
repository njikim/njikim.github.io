## Class & Instance


> - attributes & methods are inside of class
> - A method is a function that “belongs to” an object
> - instance variable contains data that is unique to each instance
> - ```__init__```: constructor, when we create an object, it initializes the object as default.
> - ```__init__(self)```: each method in class automatically takes instance as the first argument (self)


### Basic example
```python
a = 10 # local variable

class Test:
	b = 20 # class variable

print(a)
print(Test().b)
```

<pre class="output">
10
20 </pre>

<br>

```python
# creates a new instance of the class 'Test()'and assigns this object to the local variable t
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
# t1 and t2 has different id value. They are created from same Object but! instances with unique id.
print(t1)
print(t2)
```

<pre class="output">
<__main__.Test object at 0x0000000004FDA5F8>
<__main__.Test object at 0x0000000004FDA668>
</pre>

<br>

```python
t1.b = 10
t2.b = 20
print(t1.b, t2.b)
```
<pre class="output">
10
20 </pre>

<br>

### example
Create an instance called obj from Class object 'Person()'. Then, set the attributes of this instance obj one by one.
```python
class Person:
    name = str()
    age = int()
    salary = float()

obj = Person() # create an instance
obj.name = 'kimmy' # set attributes
obj.age = 30
obj.salary = 1000.0
print('name: ',obj.name, ', age: ', obj.age, ', salary: ', obj.salary)
```
<pre class="output">
name:  kimmy , age:  30 , salary:  1000.0 </pre>

<br>
In this example, create an instance called obj1 from class object 'Person1()'. Then, we can set the attributes of this instance at once by using the method called 'setItem()'. Furthermore, I've created another method called printInfo() to print the information easier.

```python
class Person1:
    name = str()
    age = int()
    salary = float()

    #method (not function)
    def setItem(self, name, age, salary):
        self.name = name
        self.age = age
        self.salary = salary

   def printInfo(self):
        print('name: {}, age: {}, salary: {}'.format(self.name, self.age, self.salary))


obj1 = Person1()
obj1.setItem('kimmy', 30, 10000)
obj1.printInfo()
```
<pre class="output">
name:  kimmy , age:  30 , salary:  1000.0
</pre>

<br>
In the previous examples, we cound set attributes to the instance by manually or by creating a regarding method. However, if we use ```__init__``` method, we can directly initialize the instance variables.

```python
class Person2:
    name = str()
    age = int()
    salary = float()

    def __init__(self, name, age, salary):
        self.name = name
        self.age = age
        self.salary = salary

    def printInfo(self): # don't forget to put self
        print('name: {}, age: {}, salary: {}'.format(self.name, self.age, self.salary))


obj2 = Person2('Kimmy', 30, 10000) # passing in info
obj2.printInfo() # same logic as below
Person2.printInfo(obj2)
```
<pre class="output">
name:  Kimmy , age:  30 , salary:  10000
name:  Kimmy , age:  30 , salary:  10000
</pre>