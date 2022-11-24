# Python 学习手册 上册

## 第一部分 使用入门

### 第一章、问答环节

#### python被人使用的原因

- 软件质量--可读性、一致性、可重用性、可维护性
- 开发者生产效率
  - 代码量少
  - 可立即运行，无需编译、链接
- 可移植性
- 标准库的支持
- 组件集成
- 乐趣

#### python 的缺点

- 执行速度慢 -- 调用c来解决，比如numpy

### 第二章、python 如何运行程序

python除了是个编程语言，但是它也是一个名为解释器的软件包。

解释器是代码与机器的计算机硬件之间的软件逻辑层。

#### python的运行结构

- 字节码编译

- python虚拟机 PVM
  - 迭代运行字节码指令的一个大循环

牢记python中真正拥有的只有运行时：完全不需要出事的编译阶段，所有的事情都是在程序运行时发生的。这甚至还包括建立函数和类的操作以及模块的链接。

### 第三章、你应当如何运行程序

#### 交互式命令行模式

可以使用譬如

```c++
python script.py > saveit.txt
```

todo

不知道为什么import this 会输出两遍

```python
import this
print("hello world")
print(2**100)
print(56)
for x in 'spam':
    print(x)
import this
///   
C:\Users\Administrator\Desktop>python this.py
hello world
1267650600228229401496703205376
56
s
p
a
m
hello world
1267650600228229401496703205376
56
s
p
a
m
///     
```



#### 系统命令行和文件

```python
import sys
print(sys.platform)
print(2**100)
x = 'spam!'
print(x*8)
----------------------------
win32
1267650600228229401496703205376
spam!spam!spam!spam!spam!spam!spam!spam!
```

#### UNIX 风格可执行脚本： #！

可执行脚本

- 第一行是特定的，脚本第一行往往以`#!`开头（hash bang , shebang）,其后紧跟着机器Python解释器的路径。
- 它们往往有可执行的权限。 在UNIX 上，往往可以使用`chmod + x file.py`来实现目的。

```python
#! /usr/local/bin/python
print('hello world')
```

可以使用env来定位python解释器。

3.3 版本后的python，可以通过#！来指定python运行版本



#### :star:模块导入和重载

在第五部分会深入学习模块和较大的程序架构

简单来说，每一个以拓展名.py结尾的python文件都是一个模块。导入操作从本质来说就是载入另一个文件，并给予读取那个文件内容的权限。

导入文件是另一种运行文件的方式。

可以用reload 重新载入模块，哪怕它已经被修改

> imp在3.4后面就不用了，，，这书还在教。。。
>
> 现在用importlib

每个模块都是一个变量包（命名空间），特别的是，每个模块都是自包含的命名空间，一个模块文件不能看到其他文件中定义的变量名。除非它显式地导入了那个文件。

作者建议使用from 而不是import，尽管可能会将命名覆盖，不过那也是编程者需要控制的。

reload不可传递

## 第二部分 类型和运算

### 第四章 介绍Python 对象类型

Python 脚本中的一切都是对象。

#### Python核心数据类型

![image-20221123094807028](Learning_Python_5th_Edition_1.assets/image-20221123094807028.png)

一旦创建了一个对象，它就和操作集合绑定了。

Python 是一种动态类型的语言，它自动跟踪你的类型而不是要求声明代码。但也是强类型语言，只能对一个对象进行适合该类型的有效操作。

数字、字符串、元组是不可变的；列表、字典和集合不是如此

##### 数字

精度不是固定不变的。

##### 字符串

序列操作

字符串具有不可变性

```python
line = 'aaa,bbb,ccc,dd\n'
line
'aaa,bbb,ccc,dd\n'
line = line.rstrip()
line
'aaa,bbb,ccc,dd'
line.split(',')
['aaa', 'bbb', 'ccc', 'dd']
line
'aaa,bbb,ccc,dd'
```

Unicode 字符串

```python
'spam'
'spam'
'spam'.encode('utf8')
b'spam' #4bytes in UTF-8
'spam'.encode('utf16')
b'\xff\xfes\x00p\x00a\x00m\x00' #encoded to 10bytes in UTF-16
```

Python 3.X 在没有显式转型的情况下，将其普通字符串和字节串混合使用

#### 列表 []（最通用）

列表是一个任意类型的对象的位置先关的有序集合。

列表比起其他语言的数组要强大太多

* 没有固定类型的约束
* 没有固定大小
* 支持嵌套

不过列表也是有边界检查的，不允许使用不存在的元素，对列表末尾外赋值也是如此。

##### 推导

```python
M = [[1,2,3],[4,5,6],[7,8,9]]
M
[[1, 2, 3], [4, 5, 6], [7, 8, 9]]
M[1]
[4, 5, 6]
col1 = [row[1] for row in M]
col1
[2, 5, 8]
diag = [M[i][i] for i in [0,1,2]]
diag
[1, 5, 9]
```

#### 字典 {}

字典是映射。通过键值对来存储对象。

允许嵌套

最终释放只需要`res = 0` 即可

字典只支持通过键来访问对象

通过排序键，在使用时使字典有序,最新版本的可以一步完成

```python
M = {'a': 100,'f':44,'c':3}
M
{'a': 100, 'f': 44, 'c': 3}

KS = list(M.keys())
KS
['a', 'f', 'c']
ks.sort()
ks
['a', 'b', 'c']
for key in KS:
    print(key,'->',M[key])

    
a -> 100
c -> 3
f -> 44

for key in sorted(M):
    print(key,'->',M[key])

a -> 100
c -> 3
f -> 44
```



#### 迭代和优化

**可迭代对象**

- 内存中物理存储的序列
- 在迭代操作情况下每次产生一个元素的对象 -- 一种虚拟的序列

**迭代协议**

​	在响应next之前先用一个对象对iter内置函数作出相应，并在结束时触发一个异常。



#### 元组 () tuple

基本上就是一个不可变的列表 

```python
T = (1,3,4,5)
T
(1, 3, 4, 5)
T + (5,6)
(1, 3, 4, 5, 5, 6)
T
(1, 3, 4, 5)
```

虽然比起列表功能少，但是要的就是它的不可变。



#### 文件

文件对象是Python代码调用电脑上存放的外部文件的主要接口。

要创建一个文件对象，需调用内置的open函数以字符串的形式传递给它一个外部的文件名以及一个可选的表示处理模式的字符串。



### 第五章 数值类型

#### 数值字面量

![image-20221123110723190](Learning_Python_5th_Edition_1.assets/image-20221123110723190.png)



#### 内置数值工具

- 表达式运算符

​		`+` `-` `*` `/` `>>` `&` 等

- 内置数学函数

  pow abs round int hex bin 等

- 工具模块

  random math等

- 一些专用于特定类型的方法

  浮点数变分数 - as_integer_ratio  		判断是否为整数 - is_integer

```python
import decimal
dVal = decimal.Decimal('-3.1415926')
print(dVal)
x = dVal.as_integer_ratio()
print(x)

-3.1415926
(-15707963, 5000000)
```



#### Python表达式运算符

运算符优先级从上到下逐渐增高

![image-20221123111549155](Learning_Python_5th_Edition_1.assets/image-20221123111549155.png)



- 混合运算遵循运算符优先级

- 括号分组子表达式

- 混合类型向上转换   int变float这样

  另外这种混合类型转换仅适用于数值类型，一般来说，python不会再别的类型之间转换。



#### 数字的实际应用

##### 数值的显示格式

```python
#字符串格式化
num = 1/3
num
0.3333333333333333
'%e' % num
'3.333333e-01'
'%4.2f' %num
'0.33'
'{0:4.2f}'.format(num)
'0.33'
```



![image-20221123141200289](Learning_Python_5th_Edition_1.assets/image-20221123141200289.png)

##### 除法

- `x / y`	经典除法和真除法，3.x后会变成真除法，无论何种类型，浮点数结果都会是保留小数部分。 
- `x // y `  向下取整除法，总是会省略结果的小数部分。
- 如果想用趋于0的截断，不管正负，就可以使用math.truec函数



##### 二、八、十六进制



```python
0o1,0o20,0o377
(1, 16, 255)
0x01,0x10,0xFF
(1, 16, 255)
0b1,0b10000,0b11111111
(1, 16, 255)
```

oct,hex,bin函数可以实现int向不同类型的转换

int函数可以实现对指定进制的转换

字符串格式化也可以用在这里

```python
'%o,%x,%x,%X' % (64, 64,255,255)
'100,40,ff,FF'
```



##### 随机

![image-20221123150329619](Learning_Python_5th_Edition_1.assets/image-20221123150329619.png)

#### 其他数值类型

##### 小数类型

小数对象很像浮点数，但是它有固定的位数和小数点。

```python
0.1+0.1+0.1-0.3
#5.551115123125783e-17

#调用Decimal的构造函数，从一个表示小数的字符串传值
from decimal import Decimal
Decimal('0.1')+Decimal('0.1')+Decimal('0.1')-Decimal('0.3')
#Decimal('0.0')

#也可以通过浮点数直接创建小数对象，但是有时候会产生默认的小数位数
Decimal(0.1)+Decimal(0.1)+Decimal(0.1)-Decimal(0.3)
Decimal('2.775557561565156540423631668E-17')
```

**设置小数精度**

```python
import decimal
decimal.getcontext().prec =4
Decimal(0.1)+Decimal(0.1)+Decimal(0.1)-Decimal(0.3)
Decimal('1.110E-17')
```

Python 3.0 后，可以使用with上下文管理器语句来临时重置小数精度。

```python
import decimal
decimal.Decimal('1.00') / decimal.Decimal('3.00')
Decimal('0.3333') #这里是因为之前已经设置为4位精度了

with decimal.localcontext() as ctx:
    ctx.prec = 2
    decimal.Decimal('1.00') / decimal.Decimal('3.00')

    
Decimal('0.33')

decimal.Decimal('1.00') / decimal.Decimal('3.00')
Decimal('0.3333')
```



##### 分数类型

```python
from fractions import Fraction
x=Fraction(1,3)
x
Fraction(1, 3)
y = x +1
y
Fraction(4, 3)
print(y)
4/3
```



**从float创建Fraction**

```python
f = 2.5
from fractions import Fraction
z = Fraction(*f.as_integer_ratio())
z
Fraction(5, 2)
float(z)
2.5
```

*是一种特殊语法，可以把一个元组展开成单独的参数。

**限制小数位数**

```python
x = Fraction(1,3)
x
Fraction(1, 3)
a = x + Fraction(*(4.0/3).as_integer_ratio())
a
Fraction(22517998136852479, 13510798882111488)
a.limit_denominator(10)
Fraction(5, 3)
```



##### 集合

集合是一些唯一的、不可变的对象的无序集合体。很像一个有键无值的字典。

集合支持与或非异或等操作

```python
x = set('abcde')
y = set('bdxyz')
x
{'b', 'a', 'e', 'd', 'c'}
y
{'b', 'd', 'z', 'y', 'x'}
x-y #x去除b
{'a', 'e', 'c'}
x|y	#并集
{'b', 'a', 'e', 'd', 'c', 'z', 'y', 'x'}
x&y	#交集
{'d', 'b'}
x ^ y	#异或集
{'a', 'c', 'z', 'y', 'e', 'x'}
x>y , x<y #是否为子集
(False, False)
```

还支持一些in，add，update等操作。

![image-20221123160929810](Learning_Python_5th_Edition_1.assets/image-20221123160929810.png)

###### 不可变性限制和冻结集合

集合只能包含不可变（可哈希化）的对象类型，因此，列表和字典不能嵌入到集合中。

集合本身是可变的，因此不能直接嵌入到其他集合里。

如果需要在另一个集合中存储一个集合，可以像调用set一样调用内置函数frozenset，创建一个不可变的集合，从而可以嵌套进其他集合里。

##### 布尔型

目前的python 有一个名为bool 的显式布尔数据类型，带有True 和False作为可用且预赋值的内置名称。

可以理解为True的值是1，但是不是数字类型。

![image-20221124171511743](Learning_Python_5th_Edition_1.assets/image-20221124171511743.png)

### 第六章 动态类型













