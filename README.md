# Trouble shooting and Little Tricks
This document contains all common questions, mistakes (I have made), and solutions while I am learning Python and Data Science. Hope this could also help for your journey to explore data science and python.
### 1. Forget to add "**,**" after every element;
### 2. Forget to add **'** to each string;
### 3. Remember to use **List Comprehension** instead of for-loop
### 4. **_"TypeError: 'int' object is not iterable"_**
Here is an example:
```python
sumlist_2 = [ mylist[i]+mylist[j] for i, j in range(0, len(mylist))] if x < j
```
output:
```python
File "<ipython-input-12-c3f2203ea261>", line 1, in <listcomp>
  sumlist_2 = [ mylist[i]+mylist[j] for i, j in range(0, len(mylist))]
TypeError: 'int' object is not iterable
```
The problem is that: two variables exist in the same list comprehension. In there case, for each variable, it needs its own range statement

the correct code:
```Python
# method 2 list compression, to sum every two elements in a given list.
sumlist_2 = [ mylist[i] + mylist[j] for i in range(0, len(mylist)) for j in range(0, len(mylist)) if i < j]
print(sumlist_2)
```
