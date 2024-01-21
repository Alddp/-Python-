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















































