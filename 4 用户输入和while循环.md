> 通过获取用户输入并学会控制程序的运行时间，你就能编写出交互式程序。

### 1 函数 input() 的工作原理

> 函数 input()让程序暂停运行，等待用户输入一些内容。获取用户输入后，Python 将其赋给 一个变量，以方便你使用。

```python
message = input("请输入您的名字：")
print(f"您的名字是：{message}")
#请输入您的名字：zhangsan
#您的名字是：zhangsan
```

函数 `input()`接受一个参数——要向用户显示的提示（prompt）或说明，让用户知道该如何做。

#### 1.1 使用 int() 来获取数值输入

使用函数 input()时，Python将用户输入解读为字符串，即使你输入一个数字。当我们需要用户输入一个数值时，可以使用 `int()`来达到这个效果。

```python
age = input("你的年龄是：")
age = int(age)
print(age > 20)
#你的年龄是：22
#True
```

#### 1.2 求模运算符

处理数值信息时，**求模运算符（%）**是个很有用的工具，它将两个数相除并返回余数：

```python
print(8 % 4) #0
print(6 % 4) #2
print(5 % 2) #1
print(10 % 4) #2
```

通过求模运算符来判断一个数是奇数还是偶数：

```python
num = input("请输入一个整数：")
num = int(num)
a = num % 2
if a == 0:
    print(f"{num}是偶数")
else:
    print(f"{num}是奇数")
#请输入一个整数：10
#10是偶数
#请输入一个整数：11
#11是奇数
```

### 2 while 循环

> for 循环用于针对集合中的每个元素都执行一个代码块，而 while 循环则不断运行，直到指 定的条件不满足为止。

#### 2.1 使用 while 循环

可使用 while 循环来数数。例如，下面的 while 循环从 1 数到 5：

```python
n = 1
while n < 6:
    print(n)
    n += 1
#1
#2
#3
#4
#5
```

#### 2.2 使用 break 退出循环

```python
num = input("请输入一个小于20，但不大于10的数：")
num = int(num)
while num < 20:
    if num > 10:
        break
    else:
        num = input("请输入一个小于20，但不大于10的数：")
        num = int(num)
```

#### 2.3 在循环中使用 continue 

要返回循环开头，并根据条件测试结果决定是否继续执行循环，可使用 `continue` 语句，它 不像 `break` 语句那样不再执行余下的代码并退出整个循环。例如，来看一个从 1 数到 10 但只打 印其中奇数的循环：

```python
current_number = 0
while current_number < 10:
    current_number += 1
    if current_number % 2 == 0:
        continue
    print(current_number)
#1
#3
#5
#7
#9
```

`continue`是跳出本次循环，`break`是直接结束整个循环。

### 3 使用 while 循环处理列表和字典

for 循环是一种遍历列表的有效方式，但不应在 for 循环中修改列表，否则将导致 Python 难 以跟踪其中的元素。要在遍历列表的同时对其进行修改，可使用 while 循环。通过将 while 循环 同列表和字典结合起来使用，可收集、存储并组织大量输入，供以后查看和显示。

#### 3.1 在列表之间移动元素

找出一个列表中的全部偶数，并添加到另一个列表中：

```python
nums1 = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
nums2 =[]
while nums1:
    num = nums1.pop()
    if num % 2 == 1:
        continue
    else:
        nums2.append(num)

print(nums2)
#[10, 8, 6, 4, 2]
```

#### 3.2 删除列表中所有指定值

```python
nums = [1, 3, 5, 6, 8, 9, 2, 3, 5, 7, 2, 1, 3, 1, 2]
while 1 in nums:
    nums.remove(1)
print(nums)
#[3, 5, 6, 8, 9, 2, 3, 5, 7, 2, 3, 2]
```



