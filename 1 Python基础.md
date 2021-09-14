## 变量和简单数据类型

### 1 变量

有关变量的规则：

:o:变量名只能包含字母、数字和下划线。变量名只能以下划线或者字母开头，不能以数字开头。例如，可以将变量命名为`message_1`或`_message1`，但不能将其命名为`1_message`.

:o:变量名不能包含空格，但能使用下划线来分隔其中的单词。例如，变量名 `greeting_message` 可行，但变量名 `greeting message` 会引发错误。

:o:不要将 Python `关键字`和`函数名`用作变量名，即不要使用 Python 保留用于特殊用途的单词， 如 `print`。

:o:变量名应既简短又具有描述性。例如，name 比 n 好，student_name 比 s_n 好，name_length 比 length_of_persons_name 好。

:o:慎用小写字母` l `和大写字母` O`，因为它们可能被人错看成数字 `1 `和` 0`。

### 2 字符串

字符串就是一系列字符。在 Python 中，用引号括起的都是字符串，其中的引号可以是单引 号，也可以是双引号，如下所示：

```python
"this is a string."
'this is also a string.'
```

#### 2.1 使用方法修改字符串的大小写

对于字符串，可执行的最简单的操作之一是修改其中单词的大小写。

```python
name = "ada love"
print(name.title())
```

结果输出`Ada Love`。

​		方法 title()以首字母大写的方式显示每个单词，即将每个单词的首字母都改为大写,其他字母改为小写。

还有其他几个很有用的大小写处理方法。例如，要将字符串改为全部大写或全部小写，可以 像下面这样做：

```python
name = "Ada Love"
print(name.upper())  #ADA LOVE
print(name.lower())  #ada love
```

#### 2.2 在字符串中使用变量

​		在有些情况下，你可能想在字符串中使用变量的值。例如，你可能想使用两个变量分别表示 名和姓，然后合并这两个值以显示姓名：

```python
first_name = "ada"
last_name = "love"
full_name = f"{first_name} {last_name}"
print(full_name)  #ada love
```

要在字符串中插入变量的值，可在前引号前加上字母 f（见），再将要插入的变量放在花括 号内。这样，当 Python 显示字符串时，将把每个变量都替换为其值。 这种字符串名为 f 字符串。f 是 format（设置格式）的简写，因为 Python 通过把花括号内的 变量替换为其值来设置字符串的格式。

使用 f 字符串可完成很多任务，如利用与变量关联的信息来创建完整的消息，如下所示：

```python
first_name = "ada"
last_name = "lovelace"
full_name = f"{first_name} {last_name}"
print(f"Hello, {full_name.title()}!") 
```

**注意:** f 字符串是 Python 3.6 引入的。如果你使用的是 Python 3.5 或更早的版本，需要使用 format() 方法，而非这种 f 语法。要使用方法 format()，可在圆括号内列出要在字符串中使用的 变量。对于每个变量，都通过一对花括号来引用。这样将按顺序将这些花括号替换为圆 括号内列出的变量的值，如下所示：

```python
full_name = "{} {}".format(first_name, last_name)
```

#### 2.3 使用制表符或换行符来添加空白

在编程中，空白泛指任何非打印字符，如空格、制表符和换行符。你可以使用空白来组织输 出，让用户阅读起来更容易。

要在字符串中添加制表符，可使用字符组合`\t`

```python
>>> print("Python")
Python
>>> print("\tPython")
	Python
```

要在字符串中添加换行符，可使用字符组合\n：

```python
>>> print("hello world")
hello world
>>> print("hello\nworld")
hello
world
```

#### 2.4 删除空白

Python 能够找出字符串开头和末尾多余的空白。要确保字符串末尾没有空白，可使用方法 `rstrip()`。

```python
>>> language='python    '
>>> language
'python    '
>>> language.rstrip()
'python'
>>> language
'python    '
```

由此可见，`rstrip()`不会更新变量，如果要把这种改变更新到变量，需要将操作结果关联到变量：

```python
>>> language=language.rstrip()
>>> language
'python'
```

还可以用`lstrip()`剔除字符串开头的空白，或者使用`strip()`同时剔除字符串两边的空白。

```python
>>> language='   python   '
>>> language.rstrip()
'   python'
>>> language.lstrip()
'python   '
>>> language.strip()
'python'
```

字符串可以用 `+` 合并（粘到一起），也可以用 `*` 重复：

```python
>>> # 3 times 'un', followed by 'ium'
>>> 3 * 'un' + 'ium'
'unununium'
```

相邻的两个或多个 *字符串字面值* （引号标注的字符）会自动合并：

```python
>>> 'Py' 'thon'
'Python'
```

这项功能只能用于两个字面值，不能用于变量或表达式：

```python
>>> str1 = 'py'
>>> str1 'thon'
SyntaxError: invalid syntax
```

但是可以使用 `+` 来合并变量与字面值。

```python
>>> str1 = 'py'
>>> str1 + 'thon'
'python'
```

字符串支持 *索引* （下标访问），第一个字符的索引是 0。单字符没有专用的类型，就是长度为一的字符串：

```python
>>> word = 'Python'
>>> word[0]
'P'
>>> word[3]
'h'
```

索引还支持负数，用负数索引时，从右边开始计数：

```python
>>> word[-1]
'n'
```

**字符串切片**

```python
>>> word[0:3]
'Pyt'
>>> word[2:5]
'tho'
```

切片索引的默认值很有用；省略开始索引时，默认值为 0，省略结束索引时，默认为到字符串的结尾：

```python
>>> word[:2]
'Py'
>>> word[2:]
'thon'
```

注意，输出结果包含切片开始，但不包含切片结束。因此，`s[:i] + s[i:]` 总是等于 `s`：

```python
>>> word[:3] + word[3:]
'Python'
>>> word[:4] + word[4:]
'Python'
```

对于使用非负索引的切片，如果两个索引都不越界，切片长度就是起止索引之差。例如， `word[1:3]` 的长度是 2。

通过所以访问字符时，索引越界会报错：

```python
>>> word[10]
Traceback (most recent call last):
  File "<pyshell#45>", line 1, in <module>
    word[10]
IndexError: string index out of range
```

但是，切片会自动处理越界索引：

```python
>>> word[1:10]
'ython'
>>> word[10:]
''
```

Python 字符串不能修改，是 immutable的。因此，为字符串中某个索引位置赋值会报错：

```python
>>> word[0] = 'O'
Traceback (most recent call last):
  File "<pyshell#50>", line 1, in <module>
    word[0] = 'O'
TypeError: 'str' object does not support item assignment 
```

### 3 数

#### 3.1 整数

在 Python 中，可对整数执行加（+）减（-）乘（*）除（/）运算。

```python
>>> 3 + 2
5
>>> 3 * 2
6
>>> 6 / 3
2.0
>>> 10 - 5
5
```

Python 使用两个乘号表示幂运算：

```python
>>> 3 ** 2
9
>>> 2 ** 3
8
>>> 10 ** 6
1000000
```

Python 还支持运算次序，因此可在同一个表达式中使用多种运算。还可以使用圆括号来修改 运算次序，让 Python 按你指定的次序执行运算，如下所示：

```python
>>> 5 + 6 * 3
23
>>> (6 + 5) * 3
33
```

在这些示例中，空格不影响 Python 计算表达式的方式。它们的存在旨在让你在阅读代码时 能迅速确定先执行哪些运算。

#### 3.2 浮点数

Python 将所有带小数点的数称为浮点数。大多数编程语言使用了这个术语，它指出了这样一 个事实：小数点可出现在数的任何位置。每种编程语言都必须细心设计，以妥善地处理浮点数， 确保不管小数点出现在什么位置，数的行为都是正常的。 

从很大程度上说，使用浮点数时无须考虑其行为。你只需输入要使用的数，Python 通常会按 你期望的方式处理它们：

```python
>>> 0.1 + 0.1
0.2
>>> 2 * 0.4
0.8
```

但需要注意的是，结果包含的小数位数可能是不确定的：

```python
>>> 0.2 + 0.1
0.30000000000000004
>>> 3 * 0.1
0.30000000000000004
```

所有语言都存在这种问题，没有什么可担心的。Python 会尽力找到一种精确表示结果的方法， 但鉴于计算机内部表示数的方式，这在有些情况下很难。就现在而言，暂时忽略多余的小数位数 即可。在第二部分的项目中，你将在需要时学习处理多余小数位的方式。

#### 3.3 整数和浮点数

将任意两个数相除时，结果总是浮点数，即便这两个数都是整数且能整除：

```python
>>> 4 / 2
2.0
```

在其他任何运算中，如果一个操作数是整数，另一个操作数是浮点数，结果也总是浮点数：

```python
>>> 1 + 2.0
3.0
>>> 2 * 3.0
6.0
>>> 3.0 ** 2
9.0 
```

无论是哪种运算，只要有操作数是浮点数，Python 默认得到的总是浮点数，即便结果原本为 整数也是如此。

#### 3.4 数中的下划线

书写很大的数时，可使用下划线将其中的数字分组，使其更清晰易读：

```python
>>> universe_age = 14_000_000_000
```

当你打印这种使用下划线定义的数时，Python 不会打印其中的下划线：

```python
>>> print(universe_age)
14000000000 
```

这是因为存储这种数时，Python 会忽略其中的下划线。将数字分组时，即便不是将每三位分 成一组，也不会影响最终的值。在 Python 看来，1000 与 1_000 没什么不同，1_000 与 10_00 也没 什么不同。这种表示法适用于整数和浮点数，但只有 Python 3.6 和更高的版本支持。

#### 3.5 同时给多个变量赋值

可在一行代码中给多个变量赋值，这有助于缩短程序并提高其可读性。这种做法最常用于将 一系列数赋给一组变量。 例如，下面演示了如何将变量 x、y 和 z 都初始化为零：

```python
>>> x,y,z=0,0,0
>>> x
0
>>> y
0
>>> z
0
```

这样做时，需要用逗号将变量名分开；对于要赋给变量的值，也需同样处理。Python 将按顺 序将每个值赋给对应的变量。只要变量和值的个数相同，Python 就能正确地将它们关联起来。

#### 3.6 常量

常量类似于变量，但其值在程序的整个生命周期内保持不变。Python 没有内置的常量类型， 但 Python 程序员会使用全大写来指出应将某个变量视为常量，其值应始终不变：

```python
MAX_CONNECTIONS = 5000
```

  在代码中，要指出应将特定的变量视为常量，可将其字母全部大写。

### 4 注释

#### 4.1 如何编写注释

 Python 中，注释用井号（#）标识。井号后面的内容都会被 Python 解释器忽略，如下所示：

```python
# 向大家问好。
print("Hello Python people!")
```

Python 解释器将忽略第一行，只执行第二行。

## 列表（list）简介

### 1 列表是什么

列表由一系列按特定顺序排列的元素组成。你可以创建包含字母表中所有字母、数字 0～9 或所有家庭成员姓名的列表；也可以将任何东西加入列表中，其中的元素之间可以没有任何关系。 列表通常包含多个元素，因此给列表指定一个表示复数的名称（如 letters、digits 或 names） 是个不错的主意。 

在 Python 中，用方括号（`[]`）表示列表，并用逗号分隔其中的元素。下面是一个简单的列 表示例，其中包含几种自行车：

```python
bicycles = ['trek','cannondale','redline','specailized']
print(bicycles)
#['trek', 'cannondale', 'redline', 'specialized']
```

如果让 Python 将列表打印出来，Python 将打印列表的内部表示，包括方括号。

#### 1.1 访问列表元素

列表是有序集合，因此要访问列表的任意元素，只需将该元素的位置（索引）告诉 Python 即可。要访问列表元素，可指出列表的名称，再指出元素的索引，并将后者放在方括号内。 例如，下面的代码从列表 bicycles 中提取第一款自行车：

```python
bicycles = ['trek','cannondale','redline','specailized']
print(bicycles[0])
#trek
```

#### 1.2 索引从`0`而不是`1`开始

在 Python 中，第一个列表元素的索引为 0，而不是 1。大多数编程语言是如此规定的，这与 列表操作的底层实现相关。

第二个列表元素的索引为 1。根据这种简单的计数方式，要访问列表的任何元素，都可将其 位置减 1，并将结果作为索引。例如，要访问第四个列表元素，可使用索引 3。

下面的代码访问索引 1 和索引 3 处的自行车：

```python
bicycles = ['trek','cannondale','redline','specailized']
print(bicycles[1])
#cannondale
print(bicycles[3])
#specailized
```

Python 为访问最后一个列表元素提供了一种特殊语法。通过将索引指定为-1，可让 Python 30 第 3 章 列表简介 返回最后一个列表元素：

```python
bicycles = ['trek','cannondale','redline','specailized']
print(bicycles[-1])
#specailized
```

这段代码返回'specialized'。这种语法很有用，因为你经常需要在不知道列表长度的情况 下访问最后的元素。这种约定也适用于其他负数索引。例如，索引-2 返回倒数第二个列表元素， 索引-3 返回倒数第三个列表元素，依此类推。

#### 1.3 使用列表中的各个值

你可以像使用其他变量一样使用列表中的各个值。例如，可以使用 f 字符串根据列表中的值 来创建消息。 

下面尝试从列表中提取第一款自行车，并使用这个值创建一条消息：

```python
bicycles = ['trek', 'cannondale', 'redline', 'specialized']
message = f"My first bicycle was a {bicycles[0].title()}."
print(message) 
#My first bicycle was a Trek.
```

### 2 修改、添加和删除元素

#### 2.1 修改列表元素

修改列表元素的语法与访问列表元素的语法类似。要修改列表元素，可指定列表名和要修改 的元素的索引，再指定该元素的新值。

```python
motorcycles = ['honda', 'yamaha', 'suzuki']
print(motorcycles)
#['honda', 'yamaha', 'suzuki'] 
motorcycles[0] = 'ducati'
print(motorcycles) 
#['ducati', 'yamaha', 'suzuki'] 
```

通过这种方法你可以修改任意列表元素的值，而不仅仅是第一个元素的值。

#### 2.2 在列表中添加元素

##### 2.2.1 在列表末尾添加元素

**语法**

```python
list.append(value)
#元素value将被添加到list的末尾
```

在列表中添加新元素时，最简单的方式是将元素附加（`append`）到列表。给列表附加元素时， 它将添加到列表末尾。继续使用前一个示例中的列表，在其末尾添加新元素'ducati'：

```python
motorcycles = ['honda', 'yamaha', 'suzuki']
print(motorcycles)
#['honda', 'yamaha', 'suzuki']
motorcycles.append('ducati')
print(motorcycles) 
#['honda', 'yamaha', 'suzuki', 'ducati']
```

方法 append()让动态地创建列表易如反掌。例如，你可以先创建一个空列表，再使用一系列 函数调用 append()来添加元素。下面来创建一个空列表，再在其中添加元素'honda'、'yamaha' 和'suzuki'：

```python
motorcycles = []
motorcycles.append('honda')
motorcycles.append('yamaha')
motorcycles.append('suzuki')
print(motorcycles)
#['honda', 'yamaha', 'suzuki']
```

##### 2.2.2 在列表中插入元素

**语法**

```python
list.insert(index,value)
```

- `index`：索引，元素将插入到指定索引。
- `value`：要插入的元素。

使用方法 insert()可在列表的任何位置添加新元素。为此，你需要指定新元素的索引和值。

```python
motorcycles = ['honda', 'yamaha', 'suzuki']
motorcycles.insert(0, 'ducati')
print(motorcycles) 
#['ducati', 'honda', 'yamaha', 'suzuki']
```

#### 2.3 从列表中删除元素

##### 2.3.1 使用del语句删除元素

```python
del list[index]
#删除指定位置的元素
```

使用 del 语句将值从列表中删除后，你就无法再访问它了。

##### 2.3.2 使用方法pop()删除元素

有时候，你要将元素从列表中删除，并接着使用它的值。例如，你可能需要获取刚被射杀的 外星人的 x 坐标和 y 坐标，以便在相应的位置显示爆炸效果；在 Web 应用程序中，你可能要将用 户从活跃成员列表中删除，并将其加入到非活跃成员列表中。 

方法 pop()删除列表末尾的元素，并让你能够接着使用它。术语弹出（pop）源自这样的类比： 列表就像一个栈，而删除列表末尾的元素相当于弹出栈顶元素。

`pop()`方法有一个返回值，返回被弹出的元素，可以用一个变量来接收。

```python
list1 = [1,2,3,4,5,6,7,8,9]
popped_num = list1.pop()
print(popped_num)
#9
print(list1)
#[1,2,3,4,5,6,7,8]
```

##### 2.3.3 弹出列表中任何位置的元素

实际上，可以使用 pop()来删除列表中任意位置的元素，只需在圆括号中指定要删除元素的 索引即可。

```python
list1 = [1,2,3,4,5,6,7,8,9]
popped_num = list1.pop(5)
print(popped_num)
#6
print(list1)
#[1,2,3,4,5,7,8,9]
```

##### 2.3.4 根据值删除元素

```python
list1 = [1,2,3,4,5,6,7,8,9]
list1.remove(5)
print(list1)
#[1,2,3,4,7,8,9]
```

有时候，你不知道要从列表中删除的值所处的位置。如果只知道要删除的元素的值，可使用 方法 remove()。

但是当一个列表中有多个值相同的时候`remove()`只会删除掉位置靠前，也就是索引值最小的那个。如果想要全部删除，就需要使用循环来确保将每个值都删除。

当你想删除一个值，但是后面还需要用到的时候，可以借用一个变量来存储这个值，如下：

```python
list1 = [1,2,3,4,5,6,7,8,9]
remove_num = 5
list1.remove(remove_num)
print(list1)
#[1,2,3,4,7,8,9]
print(remove_num)
#5
```

### 3 组织列表

#### 3.1 sort()方法对列表永久排序

```python
nums = [5, 6, 9, 42, 1, 2, 3, 8, 7]
nums.sort()
print(nums)
#[1, 2, 3, 5, 6, 7, 8, 9, 42]
```

`sort()`方法默认升序排列，如果需要降序排列，只需向 sort()方法传递参数` reverse=True `即可。

```python
nums = [5, 6, 9, 42, 1, 2, 3, 8, 7]
nums.sort(reverse=True)
print(nums)
#[42, 9, 8, 7, 6, 5, 3, 2, 1]
```

同时，`sort()`方法是一个修改列表的方法，它会改变原列表。

#### 3.2 函数sorted()对列表临时排序

函数`sorted()`会对列表进行排序并返回排序后的结果，但是不会改变原来的列表。

```python
nums = [5, 6, 9, 42, 1, 2, 3, 8, 7]
asc_nums = sorted(nums)
print(asc_nums)
#[1, 2, 3, 5, 6, 7, 8, 9, 42]
print(nums)
#[5, 6, 9, 42, 1, 2, 3, 8, 7]
```

也可向函数 sorted()传递参数 reverse=True，得到相反顺序的列表。

```python
nums = [5, 6, 9, 42, 1, 2, 3, 8, 7]
asc_nums = sorted(nums,reverse=True)
print(asc_nums)
#[42, 9, 8, 7, 6, 5, 3, 2, 1]
print(nums)
#[5, 6, 9, 42, 1, 2, 3, 8, 7]
```

#### 3.3 倒着打印列表

要反转列表元素的排列顺序，可使用方法 `reverse()`。

```python
nums = [5, 6, 9, 42, 1, 2, 3, 8, 7]
nums.reverse()
print(nums)
#[7, 8, 3, 2, 1, 42, 9, 6, 5]
```

方法 `reverse()`永久性地修改列表元素的排列顺序，但可随时恢复到原来的排列顺序，只需 对列表再次调用` reverse()`即可。

#### 3.4 确定列表的长度

使用`函数 len()`可快速获悉列表的长度。

```python
nums = [5, 6, 9, 42, 1, 2, 3, 8, 7]
nums_len = len(nums)
print(nums_len)
#9
list1 = ['a', 'd', 'c', 6, 9, 3]
list1_len = len(list1)
print(list1_len)
#6
```

## 操作列表

### 1 遍历整个列表

使用`for`循环来打印列表中所有元素：

```python
nums = [5, 6, 9, 42, 1, 2, 3, 8, 7]
for num in nums:
    print(num)
#5
#6
#9
#42
#1
#2
#3
#8
#7
```

#### 1.1 在for循环中执行更多操作

```python
nums = [5, 6, 9, 42, 1, 2, 3, 8, 7]
for num in nums:
    print(f"2 * {num} = {2 * num}")
#2 * 5 = 10
#2 * 6 = 12
#2 * 9 = 18
#2 * 42 = 84
#2 * 1 = 2
#2 * 2 = 4
#2 * 3 = 6
#2 * 8 = 16
#2 * 7 = 14
```

### 2 创建数值列表

列表非常适合用于存储数字集合，而 Python 提供了很多工具，可帮助你高效地处理数字列 表。明白如何有效地使用这些工具后，即便列表包含数百万个元素，你编写的代码也能运行得 很好。

#### 2.1 使用range()函数

Python 函数 `range()`让你能够轻松地生成一系列数。例如，可以像下面这样使用函数 range() 来打印一系列数：

```python
nums = range(1,10)
for num in nums:
    print(num)
#1
#2
#3
#4
#5
#6
#7
#8
#9
```

调用函数 `range()`时，也可只指定一个参数，这样它将从 0 开始。例如，range(6)返回数 0～5。

```python
nums = range(6)
for num in nums:
    print(num)
#0
#1
#2
#3
#4
#5
```

#### 2.2 使用range()创建数字列表

要创建数字列表，可使用函数 list()将 range()的结果直接转换为列表。如果将 range()作 为 list()的参数，输出将是一个数字列表。

```python
nums = list(range(1,5))
print(nums)
#[1, 2, 3, 4]
```

使用函数 range()时，还可指定步长。为此，可给这个函数指定第三个参数，Python 将根据 这个步长来生成数。

 例如，下面的代码打印 1～10 的偶数：

```python
even_nums = list(range(2,11,2))
print(even_nums)
#[2, 4, 6, 8, 10]
```

在这个示例中，函数 range()从 2 开始数，然后不断加 2，直到达到或超过终值（11），

使用函数 range()几乎能够创建任何需要的数集。例如，如何创建一个列表，其中包含前 10 个整数（1～10）的平方呢？在 Python 中，用两个星号（**）表示乘方运算。下面的代码演示了 如何将前 10 个整数的平方加入一个列表中：

```python
squares = []
for num in range(1,11):
    squares.append(num ** 2)
print(squares)
#[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

#### 2.3 对数字列表执行简单的统计计算

有几个专门用于处理数字列表的 Python 函数。例如，你可以轻松地找出数字列表的`最大值`、 `最小值`和`总和`：

```python
data1 = [1, 2, 3, 4, 5, 6, 7, 8, 9]
print(min(data1))
#1
print(max(data1))
#9
print(sum(data1))
#45
```

### 3 使用列表的一部分

> 以处理列表的部分元素，Python 称之为切片。

#### 3.1 切片

要创建切片，可指定要使用的第一个元素和最后一个元素的索引。与函数 `range()`一样， Python 在到达第二个索引之前的元素后停止。要输出列表中的前三个元素，需要指定索引 0 和 3， 这将返回索引为 0、1 和 2 的元素。

```python
data1 = [1, 2, 3, 4, 5, 6, 7, 8, 9]
print(data1[0:5])
#[1, 2, 3, 4, 5]
```

你可以生成列表的任意子集。例如，如果要提取列表的第二、第三和第四个元素，可将起始 索引指定为 1，并将终止索引指定为 4：

```python
data1 = [1, 2, 3, 4, 5, 6, 7, 8, 9]
print(data1[1:4])
#[2, 3, 4]
```

如果没有指定第一个索引，Python 将自动从列表开头开始：

```python
data1 = [1, 2, 3, 4, 5, 6, 7, 8, 9]
print(data1[:4])
#[1, 2, 3, 4]
```

要让切片终止于列表末尾，也可使用类似的语法。例如，如果要提取从第三个元素到列表末 尾的所有元素，可将起始索引指定为 2，并省略终止索引：

```python
data1 = [1, 2, 3, 4, 5, 6, 7, 8, 9]
print(data1[2:])
#[3, 4, 5, 6, 7, 8, 9]
```

若同时省略起始和结束索引，则创建一个和原始列表一样的切片。

```python
data1 = [1, 2, 3, 4, 5, 6, 7, 8, 9]
print(data1[:])
#[1, 2, 3, 4, 5, 6, 7, 8, 9]
```

可在表示切片的方括号内指定第三个值。这个值告诉 Python 在指定范围内每隔多少元素 提取一个。

```python
data1 = [1, 2, 3, 4, 5, 6, 7, 8, 9]
print(data1[0:7:3])
#[1, 4, 7]
```

#### 3.2 遍历切片

如果要遍历列表的部分元素，可在 for 循环中使用切片。

```python
data1 = [1, 2, 3, 4, 5, 6, 7, 8, 9]
for da in data1[0:4]:
    print(da)
#1
#2
#3
#4
```

#### 3.3 复制列表

要复制列表，可创建一个包含整个列表的切片，方法是同时省略起始索引和终止索引（[:]）。 这让 Python 创建一个始于第一个元素、终止于最后一个元素的切片，即整个列表的副本。

```python
data1 = [1, 2, 3, 4, 5, 6, 7, 8, 9]
data2 = data1[:]
print(data2)
#[1, 2, 3, 4, 5, 6, 7, 8, 9]
```

现在尝试修改两个列表的元素，发现互不影响，说明通过切片复制的列表和原列表是完全独立的。

```python
data1.append(100)
data2.append(200)
print(data1,data2)
#[1, 2, 3, 4, 5, 6, 7, 8, 9, 100] [1, 2, 3, 4, 5, 6, 7, 8, 9, 200]
```

### 4 元组

列表非常适合用于存储在程序运行期间可能变化的数据集。列表是可以修改的，这对处理网 站的用户列表或游戏中的角色列表至关重要。然而，有时候你需要创建一系列不可修改的元素， 元组可以满足这种需求。Python 将不能修改的值称为不可变的，而不可变的列表被称为元组。

#### 4.1 定义元组

`元组`看起来很像`列表`，但使用`圆括号`而非`中括号`来标识。定义元组后，就可使用索引来访问 其元素，就像访问列表元素一样。

例如，如果有一个大小不应改变的矩形，可将其长度和宽度存储在一个元组中，从而确保它 们是不能修改的：

```python
dimensions = (200, 50)
print(dimensions[0])
#200
print(dimensions[1])
#500
```

严格地说，元组是由逗号标识的，圆括号只是让元组看起来更整洁、更清晰。如果你要 定义只包含一个元素的元组，必须在这个元素后面加上逗号：

```python
my_t = (3,)
```

#### 4.2 遍历元组中的所有值

像列表一样，也可以使用 for 循环来遍历元组中的所有值：

```python
dimensions = (200, 50)
for dim in dimensions:
    print(dim)
#200
#50
```

#### 5.3 修改元组变量

虽然不能修改元组的元素，但可以给存储元组的变量赋值。因此，如果要修改前述矩形的尺寸，可重新定义整个元组：

```python
dimensions = (200, 50)
print("Original dimensions:")
for dimension in dimensions:
		print(dimension)
#200
#50
dimensions = (400, 100)
print("\nModified dimensions:")
for dimension in dimensions:
		print(dimension) 
#400
#100
```

