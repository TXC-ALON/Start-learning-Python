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



























































































