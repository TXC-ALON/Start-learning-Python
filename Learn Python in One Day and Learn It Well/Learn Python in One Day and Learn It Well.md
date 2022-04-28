# 一日速过python

## 1.Quick start

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

## 2.Variables and Operators

### define the variable

can define multiple variables at one go

```python 
userAge , useName = 24,'carl'
```

 the first letter of a variable cannot be a number

the variable names are case sensitive

advise to use the camel case notation or underscores

### the assignment sign '='



## 3.Data Types in Python

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

## 4.Make your program interactive

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

use the \ (backslash) character to escape characters that otherwise have a different meaning

(0428)



























