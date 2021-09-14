## if 语句

### 1 简单的实例

对于一个列表，把列表中不为5的数翻倍打印出来。

```python
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9]
for num in nums:
    if num == 5:
        print(num)
    else:
        print(2 * num)
#2
#4
#6
#8
#5
#12
#14
#16
#18
```

### 2 条件测试

每条 if 语句的核心都是一个值为 `True `或 `False `的表达式，这种表达式称为条件测试。Python 根据条件测试的值为 True 还是 False 来决定是否执行 if 语句中的代码。如果条件测试的值为 `True`，Python 就执行紧跟在 if 语句后面的代码；如果为 `False`，Python 就忽略这些代码。

#### 2.1 检查是否相等

大多数条件测试将一个变量的当前值同特定值进行比较。最简单的条件测试检查变量的值是 否与特定值相等：

判断是否相等需要用到`相等运算符`：`==`

```python
>>> a,b,c = 5,5,6
>>> a
5
>>> b
5
>>> c
6
>>> a ==b
True
>>> a ==c
False
>>> b ==c
False
```

#### 2.2 检查是否相等时忽略大小写

在 Python 中检查是否相等时区分大小写。例如，两个大小写不同的值被视为不相等,但如果大小写无关紧要，只想检查变量的值，可将 变量的值转换为小写，再进行比较：

```python
>>> a,b = 'alice','Alice'
>>> a == b
False
>>> a == b.lower()
True
```

#### 2.3 检查是否不相等

要判断两个值是否不等，可结合使用`!=`

```python
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9]
for num in nums:
    if num != 5:
        print(2 * num)
    else:
        print(num)
#2
#4
#6
#8
#5
#12
#14
#16
#18
```

#### 2.4 检查多个条件

你可能想同时检查多个条件。例如，有时候需要在两个条件都为 True 时才执行相应的操作， 而有时候只要求一个条件为 True。在这些情况下，关键字 and 和 or 可助你一臂之力。

##### 2.4.1 使用`and`

通过`and`关键字连接的两个或多个条件，只有在所有条件均为`True`时，整个表达式才为`True`否则为`False`。

```python
>>> age1,age2 = 22,23
>>> age1 > 20 and age2 > 20
True
>>> age1 > 20 and age2 > 30
False
```

##### 2.4.2 使用`or`

关键字 or 也能够让你检查多个条件，但只要至少一个条件满足，就能通过整个测试。仅当 两个测试都没有通过时，使用 or 的表达式才为 False。

```python
>>> num1,num2 = 30,40
>>> num1 > 20 or num2 < 50
True
>>> num1 <20 or num2 <50
True
>>> num1 < 20 or num2 >50
False
>>> num1 > 20 or num >50
True
```

从上面例子可以看出来，只要有一个表达式的值为`True`那么后面的表达式将不会再去计算结果。

#### 2.5 `in`检查特定值是否包含在列表中

要判断特定的值是否已包含在列表中，可使用关键字 `in`。

```python
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9]
print(5 in nums)
#True
```

#### 2.6 检查特定值是否不包含在列表中

还有些时候，确定特定的值未包含在列表中很重要。在这种情况下，可使用关键字 not in。

```python
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9]
print(9 not in nums)
#False
```

### 3 if 语句

#### 3.1 简单的 if 语句

最简单的 if 语句只有一个测试和一个操作：

```python
if conditional_test:
 do something
```

第一行可包含任何条件测试，而在紧跟在测试后面的缩进代码块中，可执行任何操作。如果条件测试的结果为 True，Python 就会执行紧跟在 if 语句后面的代码，否则 Python 将忽略这些 代码。

#### 3.2 if-else 语句

我们经常需要在条件测试通过时执行一个操作，在没有通过时执行另一个操作。在这种情况 下，可使用 Python 提供的 `if-else` 语句。`if-else` 语句块类似于简单的 `if `语句，但其中的 `else` 语句让你能够指定条件测试未通过时要执行的操作。

```python
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9]
for num in nums:
    if num == 5:
        print(num)
    else:
        print(2 * num)
#2
#4
#6
#8
#5
#12
#14
#16
#18
```

#### 3.3 if-elif-else 结构

我们经常需要检查超过两个的情形，为此可使用 Python 提供的 `if-elif-else` 结构。

在现实世界中，很多情况下需要考虑的情形超过两个。例如，来看一个根据年龄段收费的游 乐场：  4 岁以下免费；  4～18 岁收费 25 美元；  18 岁（含）以上收费 40 美元。

```python
age = 12
if age < 4:
		print("Your admission cost is $0.")
elif age < 18:
		print("Your admission cost is $25.")
else:
		print("Your admission cost is $40.") 
```

#### 3.4 使用多个 elif 代码块

可根据需要使用任意数量的 elif 代码块。

例如，假设前述游乐场要给老年人打折，可再添 加一个条件测试，判断顾客是否符合打折条件。下面假设对于 65 岁（含）以上的老人，可半价 （即 20 美元）购买门票：

```python
age = 12
if age < 4:
     price = 0
elif age < 18:
     price = 25
elif age < 65:
     price = 40
else:
     price = 20
print(f"Your admission cost is ${price}.")
```

### 4 使用 if 语句处理列表

#### 4.1 检查特殊元素

```python
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9]
for num in nums:
    if num == 5:
        print(num)
    else:
        print(2 * num)
#2
#4
#6
#8
#5
#12
#14
#16
#18
```

#### 4.2 确定列表不是空的

在运行 for 循环前确定列表是否为空很重要。

```python
nums = []
if nums:
    for num in nums:
        print(num)
else:
    print('empty list')
#empty list
```

### 5 设置 if 语句的格式

比较运算符的两边各加一个空格。

```python
if age < 4:
if age == 4:
if age != 4:
```















