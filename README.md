# 《Python编程：从入门到实践》



[TOC]



## 第2章--变量和简单数据类型

#### 2.3.1 使用方法修改字符串的大小写

|   使用方法    |      功能      |
| :-----------: | :------------: |
| `str.title()` |   首字母大写   |
| `str.lower()` | 转换字母为小写 |
| `str.upper()` | 转换字母为大写 |



```python
str = "hello world"
str.title() #首字母大写
str.lower() #转换字母为小写
str.upper() #转换字母为大写
```



#### 2.3.2 合并（拼接）字符串

```python
first_name = "xiao"
last_name = "ming"
full_name = first_name + " " + last_name
```



#### 2.3.3 使用制表符或换行符来添加空白

> 制表符（也叫制表位)的功能是在不使用表格的情况下在垂直方向按列对齐文本。比较常见的应用包括名单、简单列表等。也可以应用于制作页眉页脚等同一行有几个对齐位置的行。

| 符号 |  名称  | 功能                               |
| :--: | :----: | ---------------------------------- |
| `\t` | 制表符 | 打印输出会默认显示4个空格          |
| `\n` | 换行符 | 打印输出会把后面的内容显示在第二行 |
| `\r` | 回车符 |                                    |



#### 2.3.4 删除空白 

```python
mystring = "  whatsup  "
mystring.rstrip()
# 输出：'  whatsup'
mystring.lstrip()
# 输出：'whatsup  '
mystring.strip()
# 输出：'whatsup'
```

|    方法    |      功能      |
| :--------: | :------------: |
| `rstrip()` | `删除右边空白` |
| `lstrip()` | `删除左边空白` |
| `strip()`  | `删除两头空白` |



#### 2.3.5 使用字符串时避免语法错误

撇号位于两个双引号之间，因此Python解释器能够正确地理解这个字符串：

```python
message = "One of Python's strengths is its diverse community."
print(message)
```

然而，如果你使用单引号，Python将无法正确地确定字符串的结束位置：

```python
message = 'One of Python's strengths is its diverse community.'
print(message)
```



#### 2.3.6 Python 2 中的print语句

### 2.4数字

#### 2.4.1 整数

#### 2.4.2 浮点数

> *浮点数：带一个可以浮动的点的数。比如100可以写成0.1 x 10的3次方，0.01 x 10的4次方。。。这个小数点可以浮动，因此得名。*

**Python存储浮点数有三个部分：指数，小数点左边的数，小数点右边的数。**



从很大程度上说，使用浮点数时都无需考虑其行为。你只需输入要使用的数字，Python通常都会按你期望的方式处理它们：

```
0.1+0.1
0.2
0.2+0.2
0.4
2 * 0.1
0.2
2 * 0.2
0.4
```



> `不确定尾数。`
> `因为Python在计算前会将我们输入的十进制数字转换为二进制，计算后，然后将二进制的结果又转换为十进制数字显示出来。`
> `对于小数而言，因为十进制小数与二进制小数之间并不是完全对等转换的，一般来说，一个十进制小数会转换为无限位数的二进制小数，但是呢，因为计算机一般只截取无限位数中前53位，所以造成同一个小数的十进制表示结果与二进制表示结果并不等价。`
>
> ```
> 0.2+0.1
> 0.30000000000000004
> 3 * 0.1
> 0.30000000000000004
> ```
>
> `经过两次转换就造成了不确定尾数。`
> `为了解决这个问题，我们一般会采用round()函数对数据进行处理。`
>
> `**round()函数的格式：round(x,d)**`
>
> `其中x为需要被处理的数据，d为需要保留的小数位数，d=0表示取整，d=1表示保留一位小数，以此类推。另外，round()会自动四舍五入。` 
> `特别注意，整数+浮点数=浮点数，如1+3.0=4.0。因此，需要注意不确定尾数的问题。`
>
> ```python
> round(0.1+0.2,1)==0.3
> ```



#### 2.4.3 使用函数str()避免类型错误

如以下代码会引发错误:

```python
age = 23
message = "Happy "+age+"rd Birthday!"
print(message)
```

```bash
Traceback (most recent call last):
  File "D:\Codes\Python\scrapy\笔记\book.py", line 3, in <module>
    message = "Happy "+age+"rd Birthday!"
              ~~~~~~~~^~~~
TypeError: can only concatenate str (not "int") to str
```

正确方式需要将age格式化为字符串格式

```python
message = "Happy " + str(age) + "rd Birthday!"
```



#### 2.4.4 Python 2 中的整数

### 2.5 注释

#### 2.5.1 如何编写注释

```python
message = "Happy " + str(age) + "rd Birthday!"
```

#### 2.5.2 该编写什么样的注释

### 2.6 Python之禅

### 2.7 小结

1. 如何使用变量
2. 如何创建描述性变量名以及如何消除名称错误和语法错误
3. 字符串是什么，以及如何使用小写、大写和首字母大写方式显示字符串
4. 使用空白来显示整洁的输出，以及如何剔除字符串中多余的空白；如何使用整数和浮点数
5. 使用数值数据时需要注意的意外行为。



## 第3章--列表简介

### 3.1 列表是什么

> 列表由一系列["按特定顺序排列的"]元素组成。[1，'a'，1]

在Python中，用方括号[]来表示列表，并用逗号来分隔其中的元素。

```python
bicycles = ['trek','cannondale','redline','specialized']
print(bicycles)
```

打印结果:

```
['trek', 'cannondale', 'redline', 'specialized']
```



#### 3.1.1 访问列表元素

例如，下面的代码从列表bicycles中提取第一款自行车：

```python
bicycles = ['trek', 'cannondale', 'redline', 'specialized']
print(bicycles[0])
```

打印结果:

```
trek
```

#### 3.1.2 索引从`0`而不是`1`开始

#### 3.1.3 使用列表中的各个值

下面来尝试从列表中提取第一款自行车，并使用这个值来创建一条消息：

```python
bicycles = ['trek', 'cannondale', 'redline', 'specialized']
message = "My first bicycle was a " + bicycles[0].title() + "."
print(message)
```



##### 动手试一试

请尝试编写一些简短的程序来完成下面的练习，以获得一些使用Python列表的第一手经验。你可能需要为每章的练习创建一个文件夹，以整洁有序的方式存储为完成各章的练习而编写的程序。

- [ ] *3-1 姓名：将一些朋友的姓名存储在一个列表中，并将其命名为names。依次访问该列表中的每个元素，从而将每个朋友的姓名都打印出来。*

```python
names = ['陈', '许', '李', '白']
for i in range(4):
    print(names[i])
```



- [ ] *3-2 问候语：继续使用练习3-1中的列表，但不打印每个朋友的姓名，而为每人打印一条消息。每条消息都包含相同的问候语，但抬头为相应朋友的姓名。*

```python
names = ['陈', '许', '李', '白']
for i in range(4):
    print(names[i]+"你好")
```



### 3.2 修改、添加和删除元素

##### 函数汇总:

|     方法     | 功能                                                         |
| :----------: | ------------------------------------------------------------ |
| `.append()`  | 在末尾添加一个元素                                           |
| `.insert()`  | 可在列表任意位置添加元素                                     |
|    `del`     | 删除列表中指定元素，注意!使用`del`则无法再次访问该元素       |
|   `.pop()`   | 同样是删除元素，但可以再次访问（弹出 拉出）<br />* 不加参数则弹出最后一个元素<br />* 加参数则弹出指定位置元素 |
| `.remove() ` | 根据值删除元素                                               |




#### 3.2.1 修改列表元素

修改列表元素的语法与访问列表元素的语法类似。要修改列表元素，可指定列表名和要修改的元素的索引，再指定该元素的新值。
例如，假设有一个摩托车列表，其中的第一个元素为`honda`，如何修改它的值呢？

```python
motorcycles = ['honda','yamaha','suzuki'] 
print(motorcycles)
motorcycles[0] = 'ducati'
print(motorcycles)
```

输出表明，第一个元素的值确实变了，但其他列表元素的值没变：

```
['honda', 'yamaha', 'suzuki']
['ducati', 'yamaha', 'suzuki']
```



#### 3.2.2 在列表中添加元素

| `.append()` | 在末尾添加一个元素 | 例：`变量名.append('元素')` |
| ----------- | ------------------ | --------------------------- |

```python
motorcycles = ['honda', 'yamaha', 'suzuki']
print(motorcycles)
motorcycles.append('ducati')
print(motorcycles)
```

| `.insert()` | 可在列表任意位置添加元素 | 例：`变量名.insert(0,'元素')`   *注释：0表示位置* |
| :---------: | ------------------------ | ------------------------------------------------- |

```python
motorcycles = ['honda', 'yamaha', 'suzuki']
motorcycles.insert(0, 'ducati')
print(motorcycles)
```

| `del` | 删除列表中指定元素，注意!使用`del`则无法再次访问该元素 | 例：`del变量名[0]`   *注释：[0]表位置* |
| :---: | :----------------------------------------------------: | :------------------------------------: |

```python
motorcycles = ['honda', 'yamaha', 'suzuki']
print(motorcycles)
del motorcycles[0]
print(motorcycles)
```

|   方法   | 功能                                                         | 示例                                                         |
| :------: | :----------------------------------------------------------- | :----------------------------------------------------------- |
| `.pop()` | 同样是删除元素，但可以再次访问（弹出 拉出）<br />不加参数则弹出最后一个元素<br />加参数则弹出指定位置元素 | 例：`变量名1=[‘1’,’2’,’3’]``变量名2=变量名1 .pop(0)` <br/> 注释：(0)表示删除位置，默认末尾Print(‘变量名2’)    注释：再次访问已删除元素 |

```python
motorcycles = ['honda', 'yamaha', 'suzuki']
print(motorcycles)
popped_motorcycle = motorcycles.pop()  # 赋值后还可使用删除的部分
print(motorcycles)
print(popped_motorcycle)
```

| `.remove() ` | 根据值删除元素 | 例：`变量名.remove('元素')`   注释：只能删除满足条件的第一个元素，如需再次访问，将元素储存到新变量中再用`.remove()`即可 |
| :----------: | :------------: | :----------------------------------------------------------- |

> 注意　方法remove()只删除第一个指定的值。如果要删除的值可能在列表中出现多次，就需要使用循环来判断是否删除了所有这样的值。

```python
motorcycles = ['honda', 'yamaha', 'suzuki', 'ducati']
print(motorcycles)
motorcycles.remove('ducati')
print(motorcycles)
```

##### **动手试一试**

- [x] 3-4 嘉宾名单：如果你可以邀请任何人一起共进晚餐（无论是在世的还是故去的），你会邀请哪些人？请创建一个列表，其中包含至少3个你想邀请的人；然后，使用这个列表打印消息，邀请这些人来与你共进晚餐。

```python
guests = ['小明', '小红', '小高']
for i in guests:
    print(i + '可以邀请你共进晚餐吗?')
```

- [x] 3-5 修改嘉宾名单：你刚得知有位嘉宾无法赴约，因此需要另外邀请一位嘉宾。

  - [x] ·以完成练习3-4时编写的程序为基础，在程序末尾添加一条print语句，指出哪位嘉宾无法赴约。

    ```python
    guests = ['小明', '小红', '小高']
    for i in guests:
        print(i + '可以邀请你共进晚餐吗?')
    # 3.5---------------------------------
    print('小红无法赴约')
    ```

  - [x] ·修改嘉宾名单，将无法赴约的嘉宾的姓名替换为新邀请的嘉宾的姓名。

    ```python
    guests.remove('小红')
    new_guest = '小杰'
    guests.append(new_guest)
    ```

  - [x] ·再次打印一系列消息，向名单中的每位嘉宾发出邀请。

    ```python
    for i in guests:
        print(i + '可以邀请你共进晚餐吗?')
    ```

- [ ] 3-6 添加嘉宾：你刚找到了一个更大的餐桌，可容纳更多的嘉宾。请想想你还想邀请哪三位嘉宾。
  
  - [ ] ·以完成练习3-4或练习3-5时编写的程序为基础，在程序末尾添加一条print语句，指出你找到了一个更大的餐桌。
  
    ```python
    print('我找到了更大的餐桌')
    ```
    
  - [ ] ·使用insert()将一位新嘉宾添加到名单开头。
  
    ```python
    guests.insert(0, '小兰')
    ```
  
  - [ ] ·使用insert()将另一位新嘉宾添加到名单中间。
  
    ```python
    num = int(len(guests) / 2)  # 计算中间位置
    guests.insert(num, '小星')
    ```
  
  - [ ] ·使用append()将最后一位新嘉宾添加到名单末尾。
  
    ```python
    guests.append("神秘嘉宾")
    ```
  
  - [ ] ·打印一系列消息，向名单中的每位嘉宾发出邀请。
  
    ```python
    for i in guests:
        print(i + '可以邀请你共进晚餐吗?')
    ```
  
- [ ] 3-7 缩减名单：你刚得知新购买的餐桌无法及时送达，因此只能邀请两位嘉宾。
  - [ ] ·以完成练习3-6时编写的程序为基础，在程序末尾添加一行代码，打印一条你只能邀请两位嘉宾共进晚餐的消息。
  
    ```python
    print('抱歉.......')
    ```
  
  - [ ] ·使用pop()不断地删除名单中的嘉宾，直到只有两位嘉宾为止。每次从名单中弹出一位嘉宾时，都打印一条消息，让该嘉宾知悉你很抱歉，无法邀请他来共进晚餐。
  
    ```python
    for i in guests:
        if len(guests) > 2:
            sorry_name = guests.pop()
            print(sorry_name + '抱歉,..............')
    ```
  
  - [ ] ·对于余下的两位嘉宾中的每一位，都打印一条消息，指出他依然在受邀人之列。
  
    ```python
    for i in range(2):
        print(guests[i] + '可以邀请你共进晚餐吗?')
    ```
  
  - [ ] ·使用del将最后两位嘉宾从名单中删除，让名单变成空的。打印该名单，核实程序结束时名单确实是空的。
  
    ```python
    for i in range(len(guests)):
        del guests[i]
    print(guests)
    ```
  
    

### 3.3 组织列表

##### 函数汇总:

|     方法     | 作用                 |
| :----------: | -------------------- |
|  `.sort()`   | 对列表进行永久性排序 |
|  `sorted()`  | 对列表进行临时排序   |
| `.reverse()` | 倒着打印列表         |
|   `len()`    | 确定列表的长度       |



#### 3.3.1　使用方法`.sort()`对列表进行永久性排序

**按字母顺序排序:**

```python
cars = ['bmw', 'audi', 'toyota', 'subaru']
cars.sort()
print(cars)
```

**按字母逆序排序:**

```python
cars = ['bmw', 'audi', 'toyota', 'subaru']
cars.sort(reverse=True)
print(cars)
```



#### 3.3.2　使用函数`sorted()`对列表进行临时排序

```python
cars = ['bmw', 'audi', 'toyota', 'subaru']
print("Here is the original list:")
print(cars)
print("\nHere is the sorted list:")
print(sorted(cars))
print("\nHere is the original list again:")
print(cars)
```

> 注意　在并非所有的值都是小写时，按字母顺序排列列表要复杂些。决定排列顺序时，有多种解读大写字母的方式，要指定准确的排列顺序，可能比我们这里所做的要复杂。然而，大多数排序方式都基于本节介绍的知识



#### 3.3.3　倒着打印列表`.reverse()`

```python
cars = ['bmw', 'audi', 'toyota', 'subaru']
print(cars)
cars.reverse()
print(cars)
```

> 方法reverse()永久性地修改列表元素的排列顺序，但可随时恢复到原来的排列顺序，为此只需对列表再次调用reverse()即可。



#### 3.3.4　确定列表的长度`len()`

> **注意　==Python计算列表元素数时从1开始==，因此确定列表长度时，你应该不会遇到差一错误**。

###### 动手试一试

- [ ] 3-8 放眼世界：想出至少5个你渴望去旅游的地方。
  - [ ] ·将这些地方存储在一个列表中，并确保其中的元素不是按字母顺序排列的。
  - [ ] ·按原始排列顺序打印该列表。不要考虑输出是否整洁的问题，只管打印原始Python列表。
  - [ ] ·使用`sorted()`按字母顺序打印这个列表，同时不要修改它。
  - [ ] ·再次打印该列表，核实排列顺序未变。
  - [ ] ·使用`sorted()`按与字母顺序相反的顺序打印这个列表，同时不要修改它。
  - [ ] ·再次打印该列表，核实排列顺序未变。
  - [ ] ·使用`reverse()`修改列表元素的排列顺序。打印该列表，核实排列顺序确实变了。
  - [ ] ·使用`reverse()`再次修改列表元素的排列顺序。打印该列表，核实已恢复到原来的排列顺序。
  - [ ] ·使用`sort()`修改该列表，使其元素按字母顺序排列。打印该列表，核实排列顺序确实变了。
  - [ ] ·使用`sort()`修改该列表，使其元素按与字母顺序相反的顺序排列。打印该列表，核实排列顺序确实变了。
- [ ] 3-9 晚餐嘉宾：在完成练习3-4～练习3-7时编写的程序之一中，使用len()打印一条消息，指出你邀请了多少位嘉宾来与你共进晚餐。
- [ ] 3-10 尝试使用各个函数：想想可存储到列表中的东西，如山岳、河流、国家、城市、语言或你喜欢的任何东西。编写一个程序，在其中创建一个包含这些元素的列表，然后，对于本章介绍的每个函数，都至少使用一次来处理这个列表。

### 3.4 使用列表时避免索引错误

> 在python中列表的索引可以用**负数**表示，每当需要访问最后一个列表元素时，都可使用索引-1
>
> 仅当列表为空时，这种访问最后一个元素的方式才会导致错误
>



### 3.5　小结

在本章中，你学习了：列表是什么以及如何使用其中的元素；如何定义列表以及如何增删元素；如何对列表进行永久性排序，以及如何为展示列表而进行临时排序；如何确定列表的长度，以及在使用列表时如何避免索引错误



## 第4章 操作列表

### 4.1　遍历整个列表

下面使用for循环来打印魔术师名单中的所有名字：

```python
magicians = ['alice', 'david', 'carolina']
for magician in magicians:
    print(magician)
```

#### 4.1.1　深入地研究循环

> python不需要提前判定需要循环多少次，或者说循环退出设定

#### 4.1.2　在for循环中执行更多的操作



#### 4.1.3　在for循环结束后执行一些操作



### 4.2　避免缩进错误

### 4.3　创建数值列表

#### 4.3.1　使用函数`range()`

> #### `range`函数包含第一个值，不包含第二个值，存在差一动作，特别注意
`range(n1,n2,n3)`，前两个参数所描述的区间是前闭后开的，第三个参数是步长，默认为1。

#### 4.3.2 使用`range()`创建数字列表

>  要创建数字列表，可使用函数`list()`将`range()`的结果直接转换为列表。
>
> 如果将`range()`作为`list()`的参数，输出将为一个数字列表。

```python
numbers = list(range(1, 6))
print(numbers)
```



使用函数`range()`几乎能够创建任何需要的数字集，例如，如何创建一个列表，其中包含前10个整数（即1～10）的平方呢？在Python中，两个星号`**`表示乘方运算。下面的代码演示了如何将前10个整数的平方加入到一个列表中：

```python
squares = []
for value in range(1, 11):  # 通过for循环遍历列表
    square = value ** 2
    squares.append(square)  # 在列表后追加其平方值
print(squares)
```

 简化代码

```python
squares = []
for value in range(1, 11):
    squares.append(value ** 2)
print(squares)
```



#### 4.3.3　对数字列表执行简单的统计计算

有几个专门用于处理数字列表的Python函数。例如，你可以轻松地找出数字列表的最大值、最小值和总和：

| 函数    | 功能   |
| ------- | ------ |
| `mix()` | 最大值 |
| `min()` | 最小值 |
| `sum()` | 和     |

```python
digits = [1, 2, 3, 4, 5, 6, 7, 8, 9, 0]
print(min(digits))
print(max(digits))
print(sum(digits))
```

```
结果：
0
9
45
```



#### 4.3.4　**列表解析

前面介绍的生成列表squares的方式包含三四行代码，而列表解析让你只需编写一行代码就能生成这样的列表。列表解析将for循环和创建新元素的代码合并成一行，并自动附加新元素。面向初学者的书籍并非都会介绍列表解析，这里之所以介绍列表解析，是因为等你开始阅读他人编写的代码时，很可能会遇到它们。

下面的示例使用列表解析创建你在前面看到的平方数列表：

```python
squares = [value ** 2 for value in range(1, 11)]
print(squares)
```

```python
#  原代码
squares = []
for value in range(1, 11):
    squares.append(value ** 2)
print(squares)
```

##### 动手试一试

- [ ] 4-3 数到20：使用一个for循环打印数字1～20（含）。

  ```python
  for i in range(1, 21):
      print(i)
  ```

- [ ] 4-4 一百万：创建一个列表，其中包含数字1～10000，再使用一个for循环将这些数字打印出来（如果输出的时间太长，按Ctrl+C停止输出，或关闭输出窗口）。

  ```python
  arr = list(range(1, 100001))
  for i in arr:
      print(i)
  ```

- [ ] 4-5 计算1～1000000的总和：创建一个列表，其中包含数字1～1000000，再使用min()和max()核实该列表确实是从1开始，到1000000结束的。另外，对这个列表调用函数`sum()`，看看Python将一百万个数字相加需要多长时间。

  ```python
  arr = list(range(1, 1000001))
  print(min(arr))
  print(max(arr))
  print(sum(arr))
  ```

- [ ] 4-6 奇数：通过给函数`range()`指定第三个参数来创建一个列表，其中包含1～20的奇数；再使用一个for循环将这些数字都打印出来。

  ```python
  arr = list(range(1, 21, 2))
  for i in arr:
      print(i)
  ```

- [ ] 4-7 3的倍数：创建一个列表，其中包含3～30内能被3整除的数字；再使用一个for循环将这个列表中的数字都打印出来。

  ```python
  arr = list(range(3, 31, 3))
  for arr in arr:
      print(arr)
  ```

- [ ] 4-8 立方：将同一个数字乘三次称为立方。例如，在Python中，2的立方用2**3表示。请创建一个列表，其中包含前10个整数（即1～10）的立方，再使用一个for循环将这些立方数都打印出来。

  ```python
  arr = []
  for i in range(1, 11):
      arr.append(i ** 3)
  for i in arr:
      print(i)
  ```

- [ ] 4-9 立方解析：使用列表解析生成一个列表，其中包含前10个整数的立方。

  ```python
  cube = [j ** 3 for j in range(1, 11)]
  print(cube)
  ```

### 4.4　使用列表的一部分

> *处理列表的部分元素——Python称之为切片。*

#### 4.4.1　切片

要创建切片，可指定要使用的第一个元素和最后一个元素的索引。与函数range()一样，Python在到达你指定的第二个索引前面的元素后停止。要输出列表中的前三个元素，需要指定索引0～3，这将输出分别为0、1和2的元素。
下面的示例处理的是一个运动队成员列表：

```python
players = ['charles', 'martina', 'michael', 'florence', 'eli']
print(players[0:3])
```

结果：

```
['charles', 'martina', 'michael', 'florence', 'eli']
['charles', 'martina', 'michael']
```



#### 4.4.2　遍历切片

```python
players = ['charles', 'martina', 'michael', 'florence', 'eli']
print("Here are the first three players on my team:")

for player in players[:3]:  # 先且切片，在切片后的列表中遍历
    print(player.title())
```

> 在很多情况下，切片都很有用。例如，编写游戏时，你可以在玩家退出游戏时将其最终得分加入到一个列表中。然后，为获取该玩家的三个最高得分，你可以将该列表按降序排列，再创建一个只包含前三个得分的切片。处理数据时，可使用切片来进行批量处理；编写Web应用程序时，可使用切片来分页显示信息，并在每页显示数量合适的信息。

#### 4.4.3　复制列表

例如，假设有一个列表，其中包含你最喜欢的三种食品，而你还想创建另一个列表，在其中包含一位朋友喜欢的所有食品。不过，你喜欢的食品，这位朋友都喜欢，因此你可以通过复制来创建这个列表：

```python
my_foods = ['pizza', 'falafel', 'carrot cake']
friend_foods = my_foods[:]  # 类似切片方法
print("My favorite foods are:")
print(my_foods)
print("\nMy friend's favorite foods are:")
print(friend_foods)
```

> 下面将`my_foods`赋给`friend_foods`，而不是将my_foods的副本存储到`friend_foods`。**这种语法实际上是让Python将新变量`friend_foods`关联到包含在`my_foods`中的列表，因此这两个变量都指向同一个列表。**鉴于此，当我们将'`cannoli`'添加到`my_foods`中时，它也将出现在`friend_foods`中；同样，虽然'`ice cream`'好像只被加入到了`friend_foods`中，但它也将出现在这两个列表中。

> ```python
> my_foods = ['pizza', 'falafel', 'carrot cake']
> # 这行不通
> friend_foods = my_foods
> my_foods.append('cannoli')
> friend_foods.append('ice cream')
> print("My favorite foods are:")
> print(my_foods)
> print("\nMy friend's favorite foods are:")
> print(friend_foods)
> ```
>
> ```
> 结果:
> My favorite foods are:
> ['pizza', 'falafel', 'carrot cake', 'cannoli', 'ice cream']
> 
> My friend's favorite foods are:
> ['pizza', 'falafel', 'carrot cake', 'cannoli', 'ice cream']
> ```



##### 动手试一试

- [ ] 4-10 切片：选择你在本章编写的一个程序，在末尾添加几行代码，以完成如下任务。
  - [ ] ·打印消息“The first three items in the list are:”，再使用切片来打印列表的前三个元素。
  - [ ] ·打印消息“Three items from the middle of the list are:”，再使用切片来打印列表中间的三个元素。
  - [ ] ·打印消息“The last three items in the list are:”，再使用切片来打印列表末尾的三个元素。
- [ ] 4-11 你的比萨和我的比萨：在你为完成练习4-1而编写的程序中，创建比萨列表的副本，并将其存储到变量friend_pizzas中，再完成如下任务。
  - [ ] ·在原来的比萨列表中添加一种比萨。
  - [ ] ·在列表friend_pizzas中添加另一种比萨。
  - [ ] ·核实你有两个不同的列表。为此，打印消息“My favorite pizzas are:”，再使用一个for循环来打印第一个列表；打印消息“My friend's favorite pizzas are:”，再使用一个for循环来打印第二个列表。核实新增的比萨被添加到了正确的列表中。
- [ ] 4-12 使用多个循环：在本节中，为节省篇幅，程序foods.py的每个版本都没有使用for循环来打印列表。请选择一个版本的foods.py，在其中编写两个for循环，将各个食品列表都打印出来。



### 4.5 元组

#### 4.5.1　定义元组

元组看起来犹如列表，但使用**圆括号**而不是方括号来标识。定义元组后，就可以使用索引来访问其元素，就像访问列表元素一样。

例如，如果有一个大小不应改变的矩形，可将其长度和宽度存储在一个元组中，从而确保它们是不能修改的：

```python
dimensions = (200, 50)  # 定义元组
print(dimensions[0])
print(dimensions[1])
```



#### 4.5.2　遍历元组中的所有值

像列表一样，也可以使用for循环来遍历元组中的所有值



#### 4.5.3　修改元组变量

虽然不能修改元组的元素，但可以给存储元组的变量赋值。因此，如果要修改前述矩形的尺寸，可重新定义整个元组：

```python
dimensions = (200, 50)
print("Original dimensions:")
for dimension in dimensions:
    print(dimension)
dimensions = (400, 100)
print("\nModified dimensions:")
for dimension in dimensions:
    print(dimension)
```



##### 动手试一试

- [ ] 4-13 自助餐：有一家自助式餐馆，只提供五种简单的食品。请想出五种简单的食品，并将其存储在一个元组中。
  - [ ] ·使用一个for循环将该餐馆提供的五种食品都打印出来。
  - [ ] ·尝试修改其中的一个元素，核实Python确实会拒绝你这样做。
  - [ ] ·餐馆调整了菜单，替换了它提供的其中两种食品。请编写一个这样的代码块：给元组变量赋值，并使用一个for循环将新元组的每个元素都打印出来。



## 第5章 `if`语句



### 5.2.2　检查是否相等时不考虑大小写

> 网站采用类似的方式让用户输入的数据符合特定的格式。例如，网站可能使用类似的测试来确保用户名是独一无二的，而并非只是与另一个用户名的大小写不同。用户提交新的用户名时，将把它转换为小写，并与所有既有用户名的小写版本进行比较。执行这种检查时，如果已经有用户名'john'（不管大小写如何），则用户提交用户名'John'时将遭到拒绝。 

在Python中检查是否相等时区分大小写，例如，两个大小写不同的值会被视为不相等：

```bash
>>>car = 'Audi'
>>>car == 'audi'
False
```

如果大小写很重要，这种行为有其优点。但如果大小写无关紧要，而只想检查变量的值，可将变量的值转换为小写，再进行比较

```
>>> car = 'Audi'
>>> car.lower() == 'audi'
True
>>> car
'Audi'
```

无论值'`Audi`'的大小写如何，上述测试都将返回`True`，因为该测试不区分大小写。函数`lower()`不会修改存储在变量`car`中的值，因此进行这样的比较时不会影响原来的变量



#### 5.2.3　检查是否不相等

要判断两个值是否不等，可结合使用惊叹号和等号`!=`，其中的惊叹号表示不，在很多编程语言中都如此。

> 你编写的大多数条件表达式都检查两个值是否相等，但有时候检查两个值是否不等的**效率更高**。
>



#### 5.2.4　比较数字



#### 5.2.5　检查多个条件

##### 1.使用and检查多个条件

例如，要检查是否两个人都不小于21岁，可使用下面的测试：

```python
>>>age_0 = 22
>>>age_1 = 18
>>>age_0 >= 21 and age_1 >= 21
False
>>>age_1 = 22
>>>age_0 >= 21 and age_1 >= 21
True
```

为改善可读性，可将每个测试都分别放在一对括号内，但并非必须这样做。如果你使用括号，测试将类似于下面这样：

```python
(age_0 >= 21) and (age_1 >= 21)
```

##### 2.使用or检查多个条件



#### 5.2.6　检查特定值是否包含在列表中 `in`

有时候，执行操作前必须检查列表是否包含特定的值。例如，结束用户的注册过程前，可能需要检查他提供的用户名是否已包含在用户名列表中。在地图程序中，可能需要检查用户提交的位置是否包含在已知位置列表中。



要判断特定的值是否已包含在列表中，可使用关键字`in`。来看你可能为比萨店编写的一些代码；这些代码首先创建一个列表，其中包含用户点的比萨配料，然后检查特定的配料是否包含在该列表中。

```python
requested_toppings = ['mushrooms', 'onions', 'pineapple']  # 创建列表                    

if 'mushrooms' in requested_toppings:
    print('true')
print('mushrooms' in requested_toppings)
if 'pepperoni' in requested_toppings:
    print('false')
```



#### 5.2.7　检查特定值是否不包含在列表中 `not in`

还有些时候，确定特定的值未包含在列表中很重要；在这种情况下，可使用关键字`not in`。例如，如果有一个列表，其中包含被禁止在论坛上发表评论的用户，就可在允许用户提交评论前检查他是否被禁言：

```python
banned_users = ['andrew', 'carolina', 'david']  # 可以是被禁言名单
user = 'marie'  # 发表言论的用户
if user not in banned_users:  # 判断是否可以发言
    print(user.title() + ",you can post a response if you wish.")
```



#### 5.2.8　布尔表达式

随着你对编程的了解越来越深入，将遇到术语布尔表达式，它不过是条件测试的别名。与条件表达式一样，布尔表达式的结果要么为`True`，要么为`False`。

> 布尔值通常用于记录条件，如游戏是否正在运行，或用户是否可以编辑网站的特定内容：
>
> ```python
> game_active = True
> can_edit = False
> ```

##### 动手试一试

- [ ] 5-1 条件测试：编写一系列条件测试；将每个测试以及你对其结果的预测和实际结果都打印出来。你编写的代码应类似于下面这样：

> ```python
> car = 'subaru'
> print("Is car == 'subaru'?I predict True.")
> print(car == 'subaru')
>    　
> print("\nIs car == 'audi'?I predict False.")
> print(car == 'audi')
> ```

- [ ] ·详细研究实际结果，直到你明白了它为何为True或False。
- [ ] ·创建至少10个测试，且其中结果分别为True和False的测试都至少有5个。
- [ ] 5-2 更多的条件测试：你并非只能创建10个测试。如果你想尝试做更多的比较，可再编写一些测试，并将它们加入到conditional_tests.py中。对于下面列出的各种测试，至少编写一个结果为True和False的测试。
- [ ] ·检查两个字符串相等和不等。
- [ ] ·使用函数lower()的测试。
- [ ] ·检查两个数字相等、不等、大于、小于、大于等于和小于等于。
- [ ] ·使用关键字and和or的测试。
- [ ] ·测试特定的值是否包含在列表中。
- [ ] ·测试特定的值是否未包含在列表中。

#### 5.3.1 简单的`if`语句

#### 5.3.2 `if-else`语句

```python
age = 17
if age >= 18:
    print("You are old enough to vote!")
    print("Have you registered to vote yet?")
else:
    print("Sorry,you are too young to vote.")
    print("Please register to vote as soon as you turn 18!")
```



#### 5.3.3　`if-elif-else`结构

```python
age = 12
if age < 4:
    print("Your admission cost is $0.")
elif age < 18:
    print("Your admission cost is $5.")
else:
    print("Your admission cost is $10.")
```



#### 5.3.4　使用多个elif代码块

```python
age = 12
if age < 4:
    price = 0
elif age < 18:
    price = 5
elif age < 65:
    price = 10
else:
    price = 5
print("Your admission cost is $" + str(price) + ".")
```



#### 5.3.5　省略else代码块

Python并不要求if-elif结构后面必须有else代码块。在有些情况下，else代码块很有用；而在其他一些情况下，使用一条elif语句来处理特定的情形更清晰



#### 5.3.6　测试多个条件



##### 动手试一试

- [ ] 5-3 外星人颜色#1：假设在游戏中刚射杀了一个外星人，请创建一个名为alien_color的变量，并将其设置为'green'、'yellow'或'red'。
  - [ ] ·编写一条if语句，检查外星人是否是绿色的；如果是，就打印一条消息，指出玩家获得了5个点。
  - [ ] ·编写这个程序的两个版本，在一个版本中上述测试通过了，而在另一个版本中未通过（未通过测试时没有输出）。

- [ ] 5-4 外星人颜色#2：像练习5-3那样设置外星人的颜色，并编写一个if-else结构。
  - [ ] ·如果外星人是绿色的，就打印一条消息，指出玩家因射杀该外星人获得了5个点。
  - [ ] ·如果外星人不是绿色的，就打印一条消息，指出玩家获得了10个点。
  - [ ] ·编写这个程序的两个版本，在一个版本中执行if代码块，而在另一个版本中执行else代码块。

- [ ] 5-5 外星人颜色#3：将练习5-4中的if-else结构改为if-elif-else结构。
  - [ ] ·如果外星人是绿色的，就打印一条消息，指出玩家获得了5个点。
  - [ ] ·如果外星人是黄色的，就打印一条消息，指出玩家获得了10个点。
  - [ ] ·如果外星人是红色的，就打印一条消息，指出玩家获得了15个点。
  - [ ] ·编写这个程序的三个版本，它们分别在外星人为绿色、黄色和红色时打印一条消息。

- [ ] 5-6 人生的不同阶段：设置变量age的值，再编写一个if-elif-else结构，根据age的值判断处于人生的哪个阶段。
  - [ ] ·如果一个人的年龄小于2岁，就打印一条消息，指出他是婴儿。
  - [ ] ·如果一个人的年龄为2（含）～4岁，就打印一条消息，指出他正蹒跚学步。
  - [ ] ·如果一个人的年龄为4（含）～13岁，就打印一条消息，指出他是儿童。
  - [ ] ·如果一个人的年龄为13（含）～20岁，就打印一条消息，指出他是青少年。
  - [ ] ·如果一个人的年龄为20（含）～65岁，就打印一条消息，指出他是成年人。
  - [ ] ·如果一个人的年龄超过65（含）岁，就打印一条消息，指出他是老年人。

- [ ] 5-7 喜欢的水果：创建一个列表，其中包含你喜欢的水果，再编写一系列独立的if语句，检查列表中是否包含特定的水果。
  - [ ] ·将该列表命名为favorite_fruits，并在其中包含三种水果。
  - [ ] ·编写5条if语句，每条都检查某种水果是否包含在列表中，如果包含在列表中，就打印一条消息，如“You really like bananas!”。



### 5.4　使用if语句处理列表

通过结合使用if语句和列表，可完成一些有趣的任务：对列表中特定的值做特殊处理；高效地管理不断变化的情形，如餐馆是否还有特定的食材；证明代码在各种情形下都将按预期那样运行。



#### 5.4.1　检查特殊元素

#### 5.4.2　确定列表不是空的

```python
requested_toppings = []
if requested_toppings:
    for requested_topping in requested_toppings:
        print("Adding " + requested_topping + ".")
    print("\nFinished making your pizza!")
else:
    print("Are you sure you want a plain pizza?")
```

在这里，我们首先创建了一个空列表，其中不包含任何配料（见❶）。在❷处我们进行了简单检查，而不是直接执行for循环。在if语句中将列表名用在条件表达式中时，Python将在列表至少包含一个元素时返回True，并在列表为空时返回False。



## 第六章 字典



### 6.1　一个简单的字典

来看一个游戏，其中包含一些外星人，这些外星人的颜色和点数各不相同。下面是一个简单的字典，存储了有关特定外星人的信息：

```python
alien_0 = {'color': 'green', 'points': 5}
print(alien_0['color'])
print(alien_0['points'])
```



### 6.2　使用字典

在Python中，字典用放在花括号`{}`中的一系列键—值对表示，如前面的示例所示：

```python
alien_0 = {'color': 'green', 'points': 5}
```



#### 6.2.1　访问字典中的值

要获取与键相关联的值，可依次指定字典名和放在方括号内的键，如下所示：

```python
alien_0 = {'color': 'green'}
print(alien_0['color'])
```

#### 6.2.2　添加键—值对

> Python不关心键—值对的添加顺序，而只关心键和值之间的关联关系。

字典是一种动态结构，可随时在其中添加键—值对。要添加键—值对，可依次指定字典名、用方括号括起的键和相关联的值。

下面在字典`alien_0`中添加两项信息：外星人的x坐标和y坐标，让我们能够在屏幕的特定位置显示该外星人。我们将这个外星人放在屏幕左边缘，且离屏幕上边缘25像素的地方。由于屏幕坐标系的原点通常为左上角，因此要将该外星人放在屏幕左边缘，可将x坐标设置为0；要将该外星人放在离屏幕顶部25像素的地方，可将y坐标设置为25，如下所示：

```python
alien_0 = {'color': 'green', 'points': 5}
print(alien_0)
alien_0['x_position'] = 0
alien_0['y_position'] = 25
print(alien_0)
```

```
{'color': 'green', 'points': 5}
{'color': 'green', 'points': 5, 'x_position': 0, 'y_position': 25}
```



#### 6.2.3　先创建一个空字典

> 使用字典来存储用户提供的数据或在编写能自动生成大量键—值对的代码时，通常都需要先定义一个空字典。

```python
alien_0 = {}
alien_0['color'] = 'green'
alien_0['points'] = 5
print(alien_0)
```

```
{'color': 'green', 'points': 5}
```



#### 6.2.4　修改字典中的值

要修改字典中的值，可依次指定字典名、用方括号括起的键以及与该键相关联的新值。例如，假设随着游戏的进行，需要将一个外星人从绿色改为黄色：

```python
alien_0 = {'color': 'green'}
print("The alien is " + alien_0['color'] + ".")
alien_0['color'] = 'yellow'
print("The alien is now " + alien_0['color'] + ".")
```

来看一个更有趣的例子：对一个能够以不同速度移动的外星人的位置进行跟踪。为此，我们将存储该外星人的当前速度，并据此确定该外星人将向右移动多远：

```python
alien_0 = {'x_position': 0, 'y_position': 25, 'speed': 'medium'}
print("Original x-position:" + str(alien_0['x_position']))
# 向右移动外星人
# 据外星人当前速度决定将其移动多远
if alien_0['speed'] == 'slow':
    x_increment = 1
elif alien_0['speed'] == 'medium':
    x_increment = 2
else:
    # 这个外星人的速度一定很快
    x_increment = 3
# 新位置等于老位置加上增量
alien_0['x_position'] = alien_0['x_position'] + x_increment
print("New x-position:" + str(alien_0['x_position']))

```



#### 6.2.5　删除键—值对`del`

对于字典中不再需要的信息，可使用`del`语句将相应的键—值对彻底删除。使用`del`语句时，必须指定字典名和要删除的键。

例如，下面的代码从字典alien_0中删除键'points'及其值：

```python
alien_0 = {'color': 'green', 'points': 5}
print(alien_0)
del alien_0['points']
print(alien_0)
```



6.2.6　由类似对象组成的字典
在前面的示例中，字典存储的是一个对象（游戏中的一个外星人）的多种信息，但你也可以使用字典来存储众多对象的同一种信息。例如，假设你要调查很多人，询问他们最喜欢的编程语言，可使用一个字典来存储这种简单调查的结果，如下所示：

```python
favorite_languages = {
    'jen': 'python',
    'sarah': 'c',
    'edward': 'ruby',
    'phil': 'python',
}
```

##### 动手试一试

- [ ] 6-1 人：使用一个字典来存储一个熟人的信息，包括名、姓、年龄和居住的城市。该字典应包含键first_name、last_name、age和city。将存储在该字典中的每项信息都打印出来。
- [ ] 6-2 喜欢的数字：使用一个字典来存储一些人喜欢的数字。请想出5个人的名字，并将这些名字用作字典中的键；想出每个人喜欢的一个数字，并将这些数字作为值存储在字典中。打印每个人的名字和喜欢的数字。为让这个程序更有趣，通过询问朋友确保数据是真实的。
- [ ] 6-3 词汇表：Python字典可用于模拟现实生活中的字典，但为避免混淆，我们将后者称为词汇表。
  - [ ] ·想出你在前面学过的5个编程词汇，将它们用作词汇表中的键，并将它们的含义作为值存储在词汇表中。
  - [ ] ·以整洁的方式打印每个词汇及其含义。为此，你可以先打印词汇，在它后面加上一个冒号，再打印词汇的含义；也可在一行打印词汇，再使用换行符(\n)插入一个空行，然后在下一行以缩进的方式打印词汇的含义。



### 6.3 



遍历字典时默认就是遍历所有键。
`keys()`方法返回一个包含所有键的`list`
`dict.keys()`显式声明易理解。只需声明一个变量

1. 遍历键值对，for k,v in xin.items():
2. 遍历键，for k in xin.keys():
3. 遍历值，for v in xin.values():
4. 遍历按顺序的键 for k in sorted(xin.keys()):

#### 6.3.1　遍历所有的键—值对



| 方法      | 功能                | `print(user_0.items())`                                      |
| :-------- | ------------------- | :----------------------------------------------------------- |
| `.item()` | 返回一个键—值对列表 | `dict_items([('username', 'efermi'), ('first', 'enrico'), ('last', 'fermi')])` |



```python
user_0 = {
    'username': 'efermi',
    'first': 'enrico',
    'last': 'fermi',
}
for key, value in user_0.items():
    print("\nKey:" + key)
    print("Value:" + value)
```



#### 6.3.2　遍历字典中的所有键`keys()`

在不需要使用字典中的值时，方法`keys()`很有用。下面来遍历字典`favorite_languages`，并将每个被调查者的名字都打印出来：

```python
favorite_languages = {
    'jen': 'python',
    'sarah': 'c',
    'edward': 'ruby',
    'phil': 'python',
}
for name in favorite_languages.keys():
    print(name.title())
```



#### 6.3.3　按顺序遍历字典中的所有键

使用函数`sorted()`获得按特定顺序排列的键列表的副本：

```python
for name in sorted(favorite_languages.keys()):
```



#### 6.3.4　遍历字典中的所有值`values()`

如果你感兴趣的主要是字典包含的值，可使用方法`values()`，它返回一个值列表，而不包含任何键。例如，如果我们想获得一个这样的列表，即其中只包含被调查者选择的各种语言，而不包含被调查者的名字，可以这样做：

```python
for name in favorite_languages.values():
```



##### 动手试一试

- [ ] 6-4 词汇表2：既然你知道了如何遍历字典，现在请整理你为完成练习6-3而编写的代码，将其中的一系列print语句替换为一个遍历字典中的键和值的循环。确定该循环正确无误后，再在词汇表中添加5个Python术语。当你再次运行这个程序时，这些新术语及其含义将自动包含在输出中。
- [ ] 6-5 河流：创建一个字典，在其中存储三条大河流及其流经的国家。其中一个键—值对可能是'nile':'egypt'。
  - [ ] ·使用循环为每条河流打印一条消息，如“The Nile runs through Egypt.”。
  - [ ] ·使用循环将该字典中每条河流的名字都打印出来。
  - [ ] ·使用循环将该字典包含的每个国家的名字都打印出来。
  - [ ] 6-6 调查：在6.3.1节编写的程序favorite_languages.py中执行以下操作。
  - [ ] ·创建一个应该会接受调查的人员名单，其中有些人已包含在字典中，而其他人未包含在字典中。
  - [ ] ·遍历这个人员名单，对于已参与调查的人，打印一条消息表示感谢。对于还未参与调查的人，打印一条消息邀请他参与调查。



### 6.4　嵌套

有时候，需要将一系列字典存储在列表中，或将列表作为值存储在字典中，这称为嵌套。你可以在列表中嵌套字典、在字典中嵌套列表甚至在字典中嵌套字典。正如下面的示例将演示的，嵌套是一项强大的功能。

#### 6.4.1　字典列表

#### 6.4.2　在字典中存储列表





























