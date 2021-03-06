---
layout: post
title: "Comprehension"
description: "Comprehension in Python"
date: 2019-03-24
tags: [Python, Comprehension]
category: Python
comments: true
share: true
---
> - It's basically *'one line for loop'* in list, set and dictionary
> - [< loop statement > for < loop variable > in < loop range >]
> - [< loop statement > for < loop variable > in < loop range >	if < conditional statement >]

<br>

```python
data = {}
for x in range(10):
	data.append(x**2)

# apply the same logic into comprehension
data = { x**2 for x in range(10)}
print(data)
```
<pre class="output">
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81] </pre>

<br>

### Examples
```python
data1 = [ v + 2 for v in range(6)]
print(data1)
```
<pre class="output">
[2, 3, 4, 5, 6, 7] </pre>
<br>

```python
data2 = [ v + 2 for v in range(6) if v % 2 == 0]
```
<pre class="output">
[2, 4, 6] </pre>

<br>

```python
combi = []
for x in [1, 2, 3]:
	for y in [3, 1, 4]:
		if x != y:
			combi.append((x, y))

# apply the same logic into comprehension
combi = [ (x, y) for x in [1, 2, 3] for y in [3, 1, 4] if x != y ]
print(combi)
```
<pre class="output">
[(1, 3), (1, 4), (2, 3), (2, 1), (2, 4), (3, 1), (3, 4)] </pre>

<br>

### Let's see how it works on dict type!

```python
{ x : y for x, y in [(1, 'one'), (2, 'two')] }
```
<pre class="output">
{1: 'one', 2: 'two'} </pre>

<br>

```python
{ x : x + 1 for x in range(1, 4) }
```
<pre class="output">
{1: 2, 2: 3, 3: 4}
</pre>
<br>
