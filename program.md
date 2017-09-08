# 编程题

1. 编写函数，判断一个数字是否为素数，是则返回字符串YES，否则返回字符串NO。

2. 编写函数，模拟Python内置函数sorted()。

3. 编写程序，实现分段函数计算，如下表所示。

4. 编写函数，求任意整数的二进制形式中最后连续0的个数。

5. 有n个乒乓球运动员打淘汰赛，编写函数计算至少需要多少场比赛才能决出冠军，不允许直接使用n-1。

6. 编写程序，生成一个包含20个随机整数的列表，然后对其中偶数下标的元素进行降序排列，奇数下标的元素不变。（提示：使用切片。）

7. 编写程序，生成包含20个随机数的列表，然后将前10个元素升序排列，后10个元素降序排列，并输出结果。

8. 使用循环和列表推导式两种方法求解百钱买百鸡问题。假设大鸡5元一只，中鸡3元一只，小鸡1元三只，现有100元钱想买100只鸡，有多少种买法？
```
[(x,y,100-x,y) for x in range(34) for y in range(100) if 3*x+y+(100-x-y)/3 == 100]
```

9. 编写程序，在D盘根目录下创建一个文本文件test.txt，并向其中写入字符串hello world。

10. 写出下面代码的优化版本，提高运行效率。
```
x = list(range(500))
for item in x:
    t = 5**5
print(item+t)
```
```
x[499]+5**5
```

11. 编写程序，运行后用户输入4位整数作为年份，判断其是否为闰年。如果年份能被400整除，则为闰年；如果年份能被4整除但不能被100整除也为闰年。