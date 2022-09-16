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

交互式命令行模式

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

#### 模块导入和重载

在第五部分会深入学习模块和较大的程序架构

简单来说，每一个以拓展名.py结尾的python文件都是一个模块。导入操作从本质来说就是载入另一个文件，并给予读取那个文件内容的权限。













































































































