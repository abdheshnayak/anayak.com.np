---
layout: post
type: blog
title: "Python Programs with solution."
subtitle: "Some of the important python program with solution"
description: "Some of the important python program with solution"
# image: assets/images/posts/python_program.png
sortdescp: "Some of the important and Complex python programs with solutions and the output."
---

**Q1. Write a program to find all substring of a string using recursion.**

```python
def subset(br,str):
    if len(str)==0:
        return [br]
    return []+subset(br+"",str[1:])\
    +subset(br+str[0],str[1:])

print(sorted(subset("","ABC")))
```


```bash
Output:
['', 'A', 'AB', 'ABC', 'AC', 'B', 'BC', 'C']
```

**Q2. Write a recursive function to print number from n to 1.**

```python
def NtoOne(n):
    if n==0:
        return
    else:
        print(n, end=" ")
        return NtoOne(n-1)
NtoOne(5)
```

```bash
Output:
5 4 3 2 1
```

**Q3. Write a recursive function to print number from n to 1.**

```python
# Solution 1
# It will execute faster because this is tail recursive (recursion used at last of the function )
def OnetoN(index,n):
    if index == n+1:
        return
    else:
        print(index, end=" ")
        return OnetoN(index+1,n)

OnetoN(1,10)
```

```python
# Solution 2
# It will execute slower than above
def OnetoN(n):
    if n==0:
        return
    else:
        OnetoN(n-1)
        print(n, end=" ")
        return
OnetoN(10)
```

```bash
Output:
1 2 3 4 5 6 7 8 9 10
```