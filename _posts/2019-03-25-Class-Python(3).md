---
layout: post
title: "Python Class (3)"
description: "Class methods and Static methods"
date: 2019-03-25
tags: [Python, Class, Instance]
category: Python
comments: true
share: true
---
There are three types of methods in Python which are instance methods, class methods and static methods. Instance methods must have self as an argument and can access unique data of their instance. <br> 
Now, let's look at class methods and static methods!

## Class Methods & Static Methods


> - Class Methods:
>    - need to add @classmethod above the method
>    - do not need self as an argument
>    - But! they need a parameter called cls

> - Static Methods:
>    - need to add @staticmethod above the method
>    - do not need self as an arguemt
>    - do not need to instantiate an instance

### Example
```python
class Rectangle:
    width = float()
    height = float()
    cnt = 0

    def __init__(self,width,height):
        self.width = width
        self.height = height
        Rectangle.cnt += 1
    
    #instance method
    def calcArea(self): 
        area = self.width*self.height
        return area

    @staticmethod  
    def isSquare(width,height):
        return width == height

    @classmethod
    def printCount(cls):
        print(cls.cnt)

square = Rectangle.isSquare(10,10)
print(square)

r1 = Rectangle(5,5)
r2 = Rectangle(2,5)
r1.printCount()
```
<pre class="output">
True
2 
</pre>