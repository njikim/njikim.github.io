---
layout: post
title: "Python Class (2)"
description: "Class variable and Instance variable"
date: 2019-03-25
tags: [Python, Class, Instance]
category: Python
comments: true
share: true
---

## Class Variable & Instance Variable


> - Class variable: all the instances share this variable
> - Instance variable: unique for each instance

<br>

```python
class Person:
    no = 0            # class variable
    raise_amt = 1.05  # class variable

    def __init__(self, name, age, salary):
        self.name = name      # instance variable
        self.age = age        # instance variable
        self.salary = salary  # instance variable
        Person.no += 1

    def raise_sal(self):
        self.salary = int(self.salary*self.raise_amt)
```

<br>

```python
# we are going to create two instances p1 and p2. Observe the class variable 'Person.no'
print('# of instances before creating them:', Person.no)
p1 = Person('kim', 25, 100)
p2 = Person('lee', 30, 50)
print('# of instances after creating them: ', Person.no)
```
<pre class="output">
# of instances before creating them: 0
# of instances after creating them:  2
</pre>

<br>

**note:**
in a method 'raise_sal()' we have used self.raise_amt instead of Person.raise_amt. WHY? <br> both Person.raise_amt & self.raise_amt can be used. <br> -> it is possible to access class variable 'raise_amt' either by Person.raise_amt and self.raise_amt <br> -> it is possible to access class variable from class itself as well as from instances)<br> Then why self.raise_amt? <br> since it can change the value for each instance seperately

```python
# class variable is accessible by 'class name.variable name' or 'instance name.variable name'
print(Person.raise_amt) # accessed by class 
print(p1.raise_amt)     # accessed by instance 
print(p2.raise_amt)
```
<pre class="output">
1.05
1.05
1.05
</pre>

<br>

```python
#this will change all
Person.raise_amt = 1.10
print(Person.raise_amt)
print(p1.raise_amt)
print(p2.raise_amt)
```
<pre class="output">
1.1
1.1
1.1
</pre>

<br>

```python
#this will only change p1.raise_amt
p1.raise_amt = 1.03   #creating attribute('raise_amount') within emp_1
print(Person.raise_amt)
print(p1.raise_amt)
print(p2.raise_amt)
```
<pre class="output">
1.1
1.03
1.1
</pre>

