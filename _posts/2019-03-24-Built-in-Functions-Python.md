---
layout: post
title: "Lambda, Map, Filter, Reduce"
description: "Lambda, Map, Filter, Reduce function in Python"
date: 2019-03-24
tags: [Python, Lambda, Map, Filter, Reduce]
category: Python
comments: true
share: true
---

Hi! 
In this post, some useful built in functions in Python are introduced. They might not be intuitively understandable in the beginning but once you get the ideas, they are super useful! 
So let's get started.

## Lambda function
> - No limit on the parameters
> - Useful for changing the function or the value of the variables
> - key attributes on list.sort() can be implemented as well <br> (check the example below)
> - lambda parameters [ ... ] : expression 

<br>

Let's look at this python function example.
```python 
def sum(x, y):
	return x + y
result = sum(2, 3)
print(result)
```
<pre class="output">
 5 </pre>

<br>

Now, use lambda function to carry out the same result.
```python
result1 = (lambda x, y : x + y)(2, 3)
print(result1)
```
<pre class="output">
5 </pre> 

<br>

```python
func = lambda x, y : x + y
print(func(2, 3))
```
<pre class="output">
5 </pre>

<br>

```python
func1 = lambda x, y = 10 : x + y
print(func1(5))
print(func1(5, 6))
```
<pre class="output">
15
11 </pre>

<br>

```python
# mutable variable
func2 = lambda a, *b, **c : print(a, b, c)
func2(1, 2, 3, n = 4, m = 5)
```
<pre class="output">
1 (2, 3) {'n': 4, 'm': 5} </pre>

<br>

### Lambda function with list.sort()
```python
lst = [1, 5, 3, 9, 8, 4, 2]
lst.sort()
lst
```
<pre class="output">
[1, 2, 3, 4, 5, 8, 9] </pre>

<br>

```python
lst = [1, 5, 3, 9, 8, 4, 2]
lst.sort(key = lambda a : a)
lst
```
<pre class="output">
[1, 2, 3, 4, 5, 8, 9] </pre>

<br>

```python 
lst1 = [('john', 20, 100), ('sally', 10, 50), ('adriene', 30, 60)]
lst1.sort(key = lambda a : a[2])
lst1
```
<pre class="output">
[('sally', 10, 50),('adriene', 30, 60),('john', 20, 100)] </pre>

<br>

```python
# by using lower(), it changes all the alphabet into small letters then sort
lst2 = [('Aa'), ('DEF'), ('cEf')]
lst2.sort(key = lambda a : a.lower())
lst2
```
<pre class="output">
['Aa', 'cEf', 'DEF'] </pre>

<br>

## Map function
> - applies the (given) function on the (given) list and returns the result as another (iterable) list
> - map(func, iterable)

<br>

Let's see how this python function example can be simplified using map function.
```python
def calc(x):
	return x*2

b = []
for n in [1, 2, 3, 4]:
	a = calc(n)
	print(a, end = ' ')
	b.append(a)
print(b)
print(list(map(calc, [1, 2, 3, 4])))
```
<pre class="output">
[2, 4, 6, 8] 
</pre>

<br>

```python
list(map(lambda x : x**2, range(5))
```
<pre class="output">
[0, 1, 4, 9, 16] </pre>

<br>

```python
list(map(lambda x : x**2, [2, 2, 4, 5])
```
<pre class="output">
[4, 4, 16, 25] </pre>

<br>

## Reduce function
> - Mainly used for counting
> - Need to import funtools module in order to use it

<br>

```python
from functools import reduce
reduce(lambda x, y : x + y, [1, 2, 3, 4, 5])
```
<pre class="output"> 15 </pre>

<br>

```python
# when there is only one parameter, it gives you an error
# TypeError: <lambda>() takes 1 positional argument but 2 were given 
reduce(lambda x : x**2, [2, 2, 4, 5])
```

<br>

The example above could be extended as python function like this:
```python
def userReduce():
	data = [1, 2, 3, 4, 5]
	v = 0
	for i in data:
		v = v + i
	print(v)
userReduce()
```
<pre class="output"> 15 </pre>

<br>

## Filter function
> - It subtracts few parts of the data (it literally filters the data)
> - filter(func, list)

<br>

```python
list(filter(lambda x : x < 5, range(10)))
```
<pre class="output">
[0, 1, 2, 3, 4] </pre>
