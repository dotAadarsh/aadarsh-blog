---
title: Python Programming Examples | Part-1
date: 2023-01-13 00:00:00 
categories: [Technology, Programming]
tags: [python, programming, examples]
---

### Get started
Python is a powerful, versatile programming language that is widely used for web development, data analysis, artificial intelligence, and more. It's known for its simple and easy-to-learn syntax, making it a great choice for beginners.

To help you get started with Python programming, here are a few basic examples.

> To run the code, type `python <filename.py>` in the shell.
{: .prompt-info } 

#### Hello, World!

The one way to get started with any programming language is by printing `Hello, World!`. So let's print it out!

```python
# Program to print Hello, World!

print("Hello, World!")
```

```shell
Hello, World!
```
{: .nolineno }

The above code is pretty self-explanatory. We use built-in [`print()`](https://docs.python.org/3/library/functions.html#print) function to print the string `Hello, World!`. 

> string - A string is a data structure in Python that represents a sequence of characters

#### Arithmetic Operations

There are seven arithmetic operators in Python: 
- Addition (+)
- Subtraction (-)
- Multiplication (*)
- Division (/)
- Modulus (%)
- Exponentiation (**)
- Floor division (//)

```python
# Program to perform Arithmetic Operations

num1 = 15
num2 = 3

print("The sum of {0} and {1} is: {2}".format(num1, num2, num1 + num2))
print("The difference of {0} and {1} is: {2}".format(num1, num2, num1 - num2))
print("The multiplication of {0} and {1} is: {2}".format(
  num1, num2, num1 * num2))
print("The division(float) of {0} and {1} is: {2}".format(num1, num2, num1 / num2))
print("The division(floor) of {0} and {1} is: {2}".format(
  num1, num2, num1 // num2))
print("The modulus of {0} and {1} is: {2}".format(num1, num2, num1 % num2))
print("The value of {0} to the power {1} is: {2}".format(
  num1, num2, num1**num2))

```

```shell
The sum of 15 and 3 is: 18
The difference of 15 and 3 is: 12
The multiplication of 15 and 3 is: 45
The division(float) of 15 and 3 is: 5.0
The division(floor) of 15 and 3 is: 5
The modulus of 15 and 3 is: 0
The value of 15 to the power 3 is: 3375
```
{: .nolineno }

We can observe from the above code that the output statement is in the format of [`str.format(*args, **kwargs)`](https://docs.python.org/3/library/stdtypes.html#str.format). [`format()`](https://docs.python.org/3/library/string.html#format-string-syntax) method can be invoked on a string that contains literal text or replacement fields separated by brackets {}. Either the name of a keyword argument or the positional argument's numerical index is present in each replacement field. It returns a copy of the string with the string value of the relevant argument in place of each replacement field.

> Index or base index starts with 0. Why not 1? Because 0-based indexing simplifies the implementation of algorithms and makes the code more efficient by allowing for direct translation between the index of an item and its memory address, and it makes it easier to implement algorithms that work with ranges of items in an array.
{: .prompt-info }

#### Swapping

Swapping can be done in multiple ways. Let's swap two values in different methods.

`#1` - Temporary variable


```python
a = 999
b = 111

print("The value of a and b before swapping is {0} and {1}".format(a, b))

temp = a
a = b
b = temp

print("The value of a and b after swapping is {0} and {1}".format(a, b))

```

```shell
The value of a and b before swapping is 999 and 111
The value of a and b after swapping is 111 and 999
```
{: .nolineno }

We assign the value of `a` to a temporary variable called `temp`. Then assign the value of `b` to `a` and then `temp` to `b` to swap the values.

`#2` Without temporary variable - 1

```python
a = 999
b = 111

print("The value of a and b before swapping is {0} and {1}".format(a, b))

a = a + b
b = a - b
a = a - b

print("The value of a and b after swapping is {0} and {1}".format(a, b))

```

```shell
The value of a and b before swapping is 999 and 111
The value of a and b after swapping is 111 and 999
```
{: .nolineno }

`#2` Without temporary variable - 2

why not just swap it in one line? 

```python
a = 999
b = 111

print("The value of a and b before swapping is {0} and {1}".format(a, b))

a, b = b, a

print("The value of a and b after swapping is {0} and {1}".format(a, b))

```

```shell
The value of a and b before swapping is 999 and 111
The value of a and b after swapping is 111 and 999
```

The expression `a, b = b, a` is a shorthand way to swap the values of two variables in a single line of code. The expression `b, a` creates a tuple containing the values of `b` and `a` in that order. Then, the tuple is unpacked on the left-hand side of the assignment statement, with the variable `a` getting the value that was in `b`, and the variable `b` getting the value that was in `a`.

`#2` Without temporary variable - 3

Here's another method to swap by using the `XOR` operator.

```python
a = 999
b = 111

print("The value of a and b before swapping is {0} and {1}".format(a, b))

a = a ^ b
b = a ^ b
a = a ^ b

print("The value of a and b after swapping is {0} and {1}".format(a, b))

```

```shell
The value of a and b before swapping is 999 and 111
The value of a and b after swapping is 111 and 999
```
{: .nolineno }

> Suggested reading -[Bitwise Operators in Python](https://realpython.com/python-bitwise-operators/#bitwise-xor)

The `^` operator is used to perform the bitwise exclusive or (XOR) operation. The XOR operation compares each bit of the first operand to the corresponding bit of the second operand. If the bits are the same, it returns a 0 in that position. If the bits are different, it returns a 1 in that position. 

See what's happening in the above swapping process...

```
XOR Swap

original values                original values
a = 999         = 999
b = 111         = 111
do the swap                do the swap
a = a xor b     = 0b0000001111100111
b = a xor b     = 0b0000001110001000
a = a xor b     = 0b01101111
final values                final values
a               = 0b01101111
b               = 0b0000001111100111
```
{: .nolineno }

![Meme on XOR operator](/assets/media/bitwise_xor_meme.jpg){: width="327" height="440" }
_If you understand this meme, then you are good to go with the  `XOR` concept._

`#2` Without temporary variable - 4
Can you think of swapping the numbers through multiplication and division? Give it a try!

<iframe id="reddit-embed" src="https://www.redditmedia.com/r/ProgrammerHumor/comments/6jw7mr/swapping_two_integers/?ref_source=embed&amp;ref=share&amp;embed=true&amp;theme=dark" sandbox="allow-scripts allow-same-origin allow-popups" style="border: none;" height="527" width="640" scrolling="no"></iframe>

The last one (in the above meme) comes under file handling in python, Which we will explore later. If you are curious, go check out this [doc](https://pymbook.readthedocs.io/en/latest/file.html). 

#### Bit to Byte conversion

What is a Bit? According to [wiki](https://en.wikipedia.org/wiki/Bit) - "The bit is the most basic unit of information in computing and digital communications."

What is a Byte? Digital information is stored in units called bytes, which typically have eight bits.

So lets convert bits to bytes using python. In this program, we will get the input from the user to enter the number of bit. To do this we need [`input()`](https://docs.python.org/3/library/functions.html#input) function. 

From the docs: The input(prompt), if the prompt argument is present, it is written to standard output without a trailing newline. 
The function then reads a line from input, converts it to a **string** (stripping a trailing newline), and returns that.

As mentioned above, it holds the value in string. In order to convert it into integer data type. To do this, we need to do typecasting. `int()` is a constructor that allows to convert different type of value to integer, it's a built-in function and can be use to convert numbers represented as strings, floating-point numbers and other types to integers.

```python
number_of_bit = int(input("Enter the total number of bit: "))

number_of_byte = number_of_bit // 8

print("{0} bit is equals to {1} byte".format(number_of_bit, number_of_byte))
```

```shell
Enter the total number of bit: 16
16 bit is equals to 2 byte
```
{: .nolineno }

![Meme on bit and byte](/assets/media/bit_byte_meme.jpeg){: width="327" height="440" }
_Wait a minute..._

#### Positive, Negative or Zero

You know it! Basic maths...But, we will introduce some new keywords. Keywords are the reserved words that have specific meanings and restrictions around how they should be used. 

There are 35 reserved keywords in python. Those are as follows:

```
False      await      else       import     pass
None       break      except     in         raise
True       class      finally    is         return
and        continue   for        lambda     try
as         def        from       nonlocal   while
assert     del        global     not        with
async      elif       if         or         yield
```

The below program uses `if`, `elif`, and `else` keywords which are [control flow tools](https://docs.python.org/3/tutorial/controlflow.html) in python.

![Meme on bit and byte](/assets/media/elseif_meme.jpg){: width="327" height="440" }
_This meme actually explains the working of if, elif, and else._

```python
num = float(input("Enter the number: "))

if num > 0:
  print("Positive number")
elif num == 0:
  print("Zero")
else:
  print("Negative number")
```

```shell
Enter the number: -12
Negative number
```
{: .nolineno }

<iframe id="reddit-embed" src="https://www.redditmedia.com/r/ProgrammerHumor/comments/s009ad/elif_vs_elseif/?ref_source=embed&amp;ref=share&amp;embed=true&amp;theme=dark" sandbox="allow-scripts allow-same-origin allow-popups" style="border: none;" height="513" width="640" scrolling="no"></iframe>

This is just getting started. Thank you for reading! If you enjoyed this article, please feel free to share your feedback or leave a comment below. I always appreciate hearing from my readers and am happy to answer any questions you may have. you can follow me on Twitter at [@dotAadarsh](https://twitter.com/DotAadarsh). Thank you again for your support and I hope you have a great day!

