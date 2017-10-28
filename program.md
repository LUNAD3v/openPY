# 编程题

### 编写函数，判断一个数字是否为素数，是则返回字符串YES，否则返回字符串NO。

1.最笨的方法，直接循环，OJ上就等着TLE，面试就等着被刷吧～
```
import math  

def isPrime(n):  
    if n <= 1:  
    return False
    for i in range(2, int(math.sqrt(n)) + 1):  
    if n % i == 0:  
        print("NO")
    print("YES")
```
2.稍微好一点的方法，筛法：
```
n = int(input("Input value:"))
P = list(range(2,n+1))
index = 0
while True:
    for i in P[index+1:]:
        if i % P[index] == 0:
            P.remove(i)
    if P[index]**2 >= P[-1]:
        break
    index +=1

if n in P:
    print("YES")
else:
    print("NO")
```

### 编写函数，模拟Python内置函数sorted()。

Python3内置的sorted()函数使用的是一种混合的排序算法，由merge sort和insertion sort派生而来。官方解释器中sorted()函数实现在[https://github.com/python/cpython/blob/master/Objects/listobject.c](https://github.com/python/cpython/blob/master/Objects/listobject.c)
可能题目仅仅是想让我们用Python写一个排序算法，有很多方法啊～

先做个驱动程序：
```
import random

random_items = [random.randint(-50, 100) for c in range(32)]

print 'Before: ', random_items
insertion_sort(random_items)
print 'After : ', random_items
```
1. 冒泡排序
```
def bubble_sort(items):
        """ Implementation of bubble sort """
        for i in range(len(items)):
                for j in range(len(items)-1-i):
                        if items[j] &gt; items[j+1]:
                                items[j], items[j+1] = items[j+1], items[j]     # Swap!
```
2. 插入排序
```
def insertion_sort(items):
        """ Implementation of insertion sort """
        for i in range(1, len(items)):
                j = i
                while j &gt; 0 and items[j] &lt; items[j-1]:
                        items[j], items[j-1] = items[j-1], items[j]
                        j -= 1
```
3. 归并排序
```
def merge_sort(items):
        """ Implementation of mergesort """
        if len(items) &gt; 1:

                mid = len(items) / 2        # Determine the midpoint and split
                left = items[0:mid]
                right = items[mid:]

                merge_sort(left)            # Sort left list in-place
                merge_sort(right)           # Sort right list in-place

                l, r = 0, 0
                for i in range(len(items)):     # Merging the left and right list

                        lval = left[l] if l &lt; len(left) else None
                        rval = right[r] if r &lt; len(right) else None

                        if (lval and rval and lval &lt; rval) or rval is None:
                                items[i] = lval
                                l += 1
                        elif (lval and rval and lval &gt;= rval) or lval is None:
                                items[i] = rval
                                r += 1
                        else:
                                raise Exception('Could not merge, sub arrays sizes do not match the main array')
```
4. 快速排序
```
def quick_sort(items):
        """ Implementation of quick sort """
        if len(items) &gt; 1:
                pivot_index = len(items) / 2
                smaller_items = []
                larger_items = []

                for i, val in enumerate(items):
                        if i != pivot_index:
                                if val &lt; items[pivot_index]:
                                        smaller_items.append(val)
                                else:
                                        larger_items.append(val)

                quick_sort(smaller_items)
                quick_sort(larger_items)
                items[:] = smaller_items + [items[pivot_index]] + larger_items
```

### 编写程序，实现分段函数计算，如下表所示。
```
过于简单，不演示～
```

### 编写函数，求任意整数的二进制形式中最后连续0的个数。

### 有n个乒乓球运动员打淘汰赛，编写函数计算至少需要多少场比赛才能决出冠军，不允许直接使用n-1。

### 编写程序，生成一个包含20个随机整数的列表，然后对其中偶数下标的元素进行降序排列，奇数下标的元素不变。（提示：使用切片。）

### 编写程序，生成包含20个随机数的列表，然后将前10个元素升序排列，后10个元素降序排列，并输出结果。

5,6两题思路一样，先打一个随机列表：
```
import random
lst = [random.randint(0,89) for c in range(20)]
```

第6题：
```
list(sorted(lst[0:10]))+list(reversed(lst[10:21]))
```

### 使用循环和列表推导式两种方法求解百钱买百鸡问题。假设大鸡5元一只，中鸡3元一只，小鸡1元三只，现有100元钱想买100只鸡，有多少种买法？
```
[(x,y,100-x,y) for x in range(21) for y in range(33) if 5*x+3*y+(100-x-y)/3 == 100]
```

### 编写程序，在D盘根目录下创建一个文本文件test.txt，并向其中写入字符串hello world。
```
过于简单，不演示～
```

### 写出下面代码的优化版本，提高运行效率。
```
x = list(range(500))
for item in x:
    t = 5**5
print(item+t)
```
很无语的一道题，想不通连续计算499遍5^5的意义在哪儿...
```
x[499]+5**5
```

### 编写程序，运行后用户输入4位整数作为年份，判断其是否为闰年。如果年份能被400整除，则为闰年；如果年份能被4整除但不能被100整除也为闰年。
```
过于简单，不演示～
```
