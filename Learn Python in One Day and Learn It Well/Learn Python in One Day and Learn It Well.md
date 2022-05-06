# 一日速过python

## 1、2.Quick start

**the features of python**

1. easy to learn
2. take fewer lines than other language to solve the problem
3. come with an extensive collection of third party resources
4. can be used for a large variety of tasks
5. a cross platform

**the first program**

```python
2+3
3>2
print ('Hello world!')

'''
to use three three quotes(or three double quotes) for multiline comments
'''
```

## 3.Variables and Operators

### define the variable

can define multiple variables at one go

```python 
userAge , useName = 24,'carl'
```

 the first letter of a variable cannot be a number

the variable names are case sensitive

advise to use the camel case notation or underscores

### the assignment sign '='



## 4.Data Types in Python

| Data Type | Description                     |
| --------- | ------------------------------- |
| Integers  | numbers with no decimal parts   |
| Float     | numbers that have decimal parts |
| string    | text                            |

### Formatting Strings 

1. using the % Operator

   placeholders will be replaced with the variables

   (这里的’有问题，代码直接复制有错，理解就行，懒得改了)

```python
brand = ‘Apple’ 
exchangeRate = 1.235235245 
message = ‘The price of this %s laptop is %d USD and the exchange rate is %4.2f USD to 1 EUR’ %(brand, 1299, exchangeRate)
```

2. using the <font color='cornflowerblue'>format() method</font>

   ```python
   message = ‘The price of this {0:s} laptop is {1:d} USD and the exchange rate is {2:4.2f} USD to 1 EUR’.format(‘Apple’, 1299, 1.235235245)
   ```

   Inside the <font color='red'>curly</font> bracket, we first write the position of the parameter to use, followed by a <font color='red'>colon</font>. 

   After the colon, we write the formatter. 

   **<font color='orange'>There should not be any spaces within the curly brackets.</font>** 

3. don't format the string 

   ```python
   message = ‘The price of this {} laptop is {} USD and the exchange rate is {} USD to 1 EUR’.format(‘Apple’, 1299, 1.235235245)
   ```

### Type Casting

There are three built-in functions in Python that allow us to do type casting. These are the int(), float(), and str() functions.



### List

List refers to a collection of data which are normally related. 

use the <font color='cornflowerblue'>append() method</font> mentioned below to add items to the list

#### Slice

Whenever we use the slice notation in Python, the item at the start index is always included, but **<font color='orange'>the item at the end is always excluded</font>**. 

```python
price = [122,344,-54,23,"hello",23,55,3.312,44]
print (price)
[122, 344, -54, 23, 'hello', 23, 55, 3.312, 44]
print (price[2])
-54
print (price[1:3])
[344, -54]
price[4] = 0
print(price)
[122, 344, -54, 23, 0, 23, 55, 3.312, 44]
price.append("world")
print(price)
[122, 344, -54, 23, 0, 23, 55, 3.312, 44, 'world']
del price[:3]
print(price)
[23, 0, 23, 55, 3.312, 44, 'world']
```

### Tuple

Tuples are just like lists, but you cannot modify their values.

```python
monthsOfYear = (“Jan”, “Feb”, “Mar”, “Apr”, “May”, “Jun”, “Jul”, “Aug”, “Sep”, “Oct”, “Nov”, “Dec”)
```

### Dictionary

Dictionary is a collection of related data PAIRS. 

```python
userNameAndAge = {“Peter”:38, “John”:51, “Alex”:13, “Alvin”:“Not Available”} 

```

You can also declare a dictionary using the <font color='cornflowerblue'>dict( ) method</font>. To declare the userNameAndAge dictionary above, you write 

```python
userNameAndAge = dict(Peter = 38, John = 51, Alex = 13, Alvin = “Not Available”) 
```

To remove items from a dictionary, we write del dictionaryName[dictionary key].

```python
mydict = {"one":1.35, 2.5:"two point five",3:'+',7.9:2}
print (mydict)
print(mydict['one'])
print(mydict["one"])
mydict[2.5] = "two and a half"
print(mydict)
mydict["new item"] = 3.12
print(mydict)
del mydict["one"]
print(mydict)
'''
{'one': 1.35, 2.5: 'two point five', 3: '+', 7.9: 2}
1.35
1.35
{'one': 1.35, 2.5: 'two and a half', 3: '+', 7.9: 2}
{'one': 1.35, 2.5: 'two and a half', 3: '+', 7.9: 2, 'new item': 3.12}
{2.5: 'two and a half', 3: '+', 7.9: 2, 'new item': 3.12}
'''
```

## 5.Make your program interactive

our program needs to be able to prompt us for information and display them on the screen-----------Two built-in functions can do that for us: input() and print()

```python
myName = input("Please enter your name: ") 
myAge = input("What about your age: ") 

print ("Hello World, my name is", myName, "\nand I am", myAge, "years old.")

Hello World, my name is 5 
and I am 6 years old.
myName
'5'
```

### input & output

#### input()

stores the information **<font color='orange'>as a string</font>** in the variable

#### print()

The print() function is used to display information to users. It accepts zero or more expressions as parameters, separated by<font color='red'> commas</font>. 

you can use the triple quotes to span your message over multiple lines

```python
print (‘’’Hello World. 
       My name is James 
       and I am 20 years old.’’’)
```

### Escape Characters

use the \ (backslash) character to escape characters that otherwise have a different meaning,

## 6.Making choices and decisions

### condition statement

before make choices, we need to know the condition statements to control the flow

```python
== != > >=  < <= 
and or not
```

### If Statement

```python
if condition 1 is met: 
    do A 
elif condition 2 is met:
    do B 
elif condition 3 is met: 
    do C 
elif condition 4 is met: 
    do D 
else:
    do E
```

python use <font color='#DB4437'>indentation</font> 缩排 not the () {} to define the condition block of the code.

### Inline if

```python
do Task A if condition is true else do Task B
```

### For Loop

```python
for a in iterable: 
    print (a) 
    
    
    
#loop through the list
pets = ['cats', 'dogs', 'rabbits', 'hamsters']
for myPets in pets: 
    print (myPets)   
#use the enumerate to display the index
for index, myPets in enumerate(pets): 
    print (index, myPets)    
#loop through a string    
message = ‘Hello’ 
for i in message: 
    print (i)
```

#### range

The range() function generates a list of numbers and has the syntax range (start, end, step). 

```python
for i in range(5):
    print(i)
```



### While Loop

```python
while condition is true: 
    do A
```

### Break

 exit the entire loop when a certain condition is met. 

### Continue

When we use continue, the rest of the loop after the keyword is skipped for that iteration.

### :star:Try , Except

```python
try:
    do something 
except: 
    do something else when an error occurs
    
try:
    answer =12/0 
    print (answer) 
except: 
    print (“An error occurred”)
 
```

报错机制

```python
try:
    userInput1 = int(input("Please enter a number: ")) 
    userInput2 = int(input("Please enter another number: "))
    answer =userInput1/userInput2 
    print ("The answer is ", answer) 
    myFile = open("missing.txt", 'r') 
except ValueError: 
    print ("Error: You did not enter a number") 
except ZeroDivisionError: 
    print ("Error: Cannot divide by zero") 
except Exception as e: 
    print ("Unknown error: ", e)
```

### the usual exception in python 

| 异常              | 描述                                                         |
| :---------------- | :----------------------------------------------------------- |
| AssertionError    | assert（断言）语句失败                                       |
| AttributeError    | 试图访问一个对象没有的属性，比如foo.x ，但是foo没有x这个属性。 |
| IOError           | 输入/输出异常，基本上是无法打开文件。                        |
| ImportError       | 无法引入模块或者包，基本上是路径问题                         |
| IndentationError  | 语法错误，代码没有正确对齐                                   |
| IndexError        | 下标索引超出序列边界，比如当x只有三个元素，却试图访问x[5]    |
| KeyError          | 试图访问字典里不存在的键                                     |
| KerboardInterrupt | Ctrl + C 被按下                                              |
| NameError         | 使用一个还未被赋值予对象的变量                               |
| SyntaxError       | Python代码非法，代码不能解释                                 |
| TypeError         | 传入对象类型与要求的不符                                     |
| UnboundLocalError | 试图访问一个还未被设置的局部变量，基本上是由于另一个同名的全局变量，导致你以为正在访问它 |
| ValueError        | 传入一个调用者不期望的值，即使值的类型是正确的               |

https://docs.python.org/3/library/exceptions.html

## 7.Functions and Modules

Functions are simply pre-written codes that perform a certain task. 



```python
def functionName(parameters):
    code detailing what the function should do 
    return [expression]
```



### Variable Scope

Variables defined inside a function are treated differently from variables defined outside. 

Firstly, any variable declared inside a function is only accessible within the function. These are known as local variables. Any variable declared outside a function is known as a global variable and is accessible anywhere in the program. 



The second concept to understand about variable scope is that if a local variable shares the same name as a global variable, any code inside the function is accessing the local variable. 

Any code outside is accessing the global variable. Try running the code below 

```python
message1 = "Global Variable (shares same name as a local variable)" 
def myFunction(): 
    message1 = "Local Variable (shares same name as a global variable)" 
    print("\nINSIDE THE FUNCTION") 
    print (message1) 

# Calling the function 
myFunction() 

# Printing message1 OUTSIDE the function 
print ("\nOUTSIDE THE FUNCTION") 
print (message1)


INSIDE THE FUNCTION
Local Variable (shares same name as a global variable)

OUTSIDE THE FUNCTION
Global Variable (shares same name as a local variable)
```



### Importing Modules

```python
import random
for i in range(100):
    i=random.randrange(2222,11111)
    print(i)
```



### Creating our Own Module

Say you created a folder named ‘MyPythonModules’ in your C drive to store prime.py



## 8.Working with Files

### Opening and Reading Text Files

```python
f = open (‘myfile.txt’, 'r')
firstline = f.readline() 
secondline = f.readline() 
print (firstline) 
print (secondline) 
f.close()
```

#### the two Parameters

The first parameter is the path to the file. If you did not save fileOperation.py and 

myfile.txt in the same folder (desktop in this case), you need to replace ‘myfile.txt’ 

with the actual path where you stored the text file. For instance, if you stored it in a folder named ‘PythonFiles’ in your C drive, you have to write ‘C:\\PythonFiles\\myfile.txt’ (with double backslash \\). 

The second parameter is the mode. This specifies how the file will be used. The commonly used modes are 

**'r'** mode: For reading only. 

**'w'** mode: For writing only

​	If the specified file does not exist, it will be created. 

​	If the specified file exists, any existing data on the file will be erased. 

**'a'** mode: For appending. 

​	If the specified file does not exist, it will be created. 

​	If the specified file exist, any data written to the file is automatically added to the end 

**'r+'** mode: For both reading and writing. 



#### Using a For Loop to Read Text Files

```python
f = open (‘myfile.txt’, 'r') 
for line in f: 
    print (line, end = ‘’) 
f.close()
```

### Writing to a Text File

```python
f = open (‘myfile.txt’, 'a') 
f.write(‘\nThis sentence will be appended.’) 
f.write(‘\nPython is Fun!’) 
f.close()
```

### Opening and Reading Text Files by Buffer Size

Sometimes, we may want to read a file by buffer size so that our program does not use too much memory resources. 

```python
inputFile = open (‘myfile.txt’, 'r') 
outputFile = open (‘myoutputfile.txt’, 'w') 
msg = inputFile.read(10) 
while len(msg): 
    outputFile.write(msg) 
    msg = inputFile.read(10) 
inputFile.close()
outputFile.close()
```

### Opening, Reading and Writing Binary Files

Binary files refer to any file that contains non-text, such as image or video files. 

To work with binary files, we simply use the ‘rb’ or ‘wb’ mode. 

```python
inputFile = open (‘myimage.jpg’, 'rb') 
outputFile = open (‘myoutputimage.jpg’, 'wb')
```

### **Deleting and Renaming Files** 

```python
remove('myfile.txt')
rename('oldfile.txt','newfile.txt')
```



























