---
layout: article
title:  "List Comprehension (Python)"
date:   2018-02-24
categories: development
image:
    teaser: ptptea.png
    feature: ptipsf.jpg
comments: true
---

As a freshman and aspiring Computer Science major, I am taking an "Intro to Programming" course that utilizes Python as its foundational language. This class has been fairly trivial for me, mostly because I was "introduced" to programming at a very young age. Therefore I have already learned how to "think like a coder", a skill which I know can take awhile to gain for some novices. However, I always like to introduce new, shorter, and better ways to do things as my classmates start to understand each concept. That way they don't have to realize they have been doing something the long way for years like I often have.

With this in mind, I'd like to share one really awesome trick I discovered about a month ago within Python. For intermediate to advanced Python users, this will be nothing special. But for emerging novices (like myself), this can save you a lot of time. It's called "list comprehension".

#### What is List Comprehension?

Put simply, "List Comprehension" is just a way of making a list in Python. The syntax looks like this:

```python
new_list = [expression(i) for i in old_list if filter(i)]
```

If you are still new to python, that might look a little strange. After all, it would seem that you shouldn't be able to start a for loop within a list declaration. But the beauty of this statement becomes clear when you realize it is simply shorthand for a much longer statement that looks like this:

```python
new_list = []
for i in old_list:
    if filter(i):
        new_list.append(expressions(i))
```

In the program above, you must first initialize your list, then iterate over some iteratable - appending elements depending on whatever condition(s) you define. With list comprehension, you can achieve this all in one, easy to read line.

#### Example

Lets say we want to generate and print a list of integers given 15 random floats:

```python
from random import uniform
from math import ceil, floor

rlist = []

for i in range(15):
  rlist.append( round( uniform(1.0, 50.0) ) )

print(rlist)
```

Using list comprehension we can write the same program in two lines (excluding the `import` headers):

```python
from random import uniform
from math import ceil, floor

rlist = [ round( uniform(1.0, 50.0) ) for i in range(15) ]

print(rlist)
```

Clearly the second example is much quicker and more concise. In a program that uses a lot of for loops to initialize it's lists - especially fairly uncomplicated for loops - this technique can really improve the workflow. It may be far from a magical piece of python advice that will sky-rocket you to the pinnacle of mastery, but I believe it definitely helps to have it tucked away in your tool belt. I have definitely used this method quite a lot since discovering it.

I hope to keep up posts like this in the future - just so I can share cool little things I learn about Python as I go along. Next up **Ternary Functions**!
