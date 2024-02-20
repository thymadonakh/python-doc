---
weight: 2
title: "Variables and Data Types"
description: ""
icon: "article"
date: "2024-02-20T15:49:15+08:00"
lastmod: "2024-02-20T15:49:15+08:00"
draft: false
toc: true
---

## Variables

Imagine variables just like boxes that can store different thing. And you can give the name to the box, so it's easy to find next time.

```python
name = 'Gemini'
age = 1
isHuman = False

# use print() function to print it out

print(name)
print(age)
print(isHuman)
```

Now let say we wanna be more descriptive instead of the value.

```python
print("Name:", name)
print("Age:", age)
print("Is Human:", isHuman)
```

You can just add "String" with comma and then variable name to output.

Now let's say we want the value of variable from the user. We can use input() to do that.

```python
name = input('what is your name? ')
print('Your name is', name)
```

You see that, whatever you type in. It will give output the same.
But what if you ask for age and the user not giving you the number. How to make sure you get the answer you want?

Well, you can set type of input.

```python
age = int(input('How old are you? '))
print("You entered:", age)
```

If you try to input other than number value, it will give the errors message.

But the errors like that is not useful for our users to underestand what they did wrong. We can make it users friendly like by ```try``` and ```except```.

```try``` will do what they need to do when it's not errors
```except``` will do opposite like giving the error message

```python

try:
    age = int(input('How old are you? '))
    print("You entered:", age)
except ValueError:
    print("Error: Please enter a valid number for your age.")
```

But it's not very useful when it only give the messages to the users, but it also stop running. So now we want to keep running and giving feedback *until* we get the right answer.

To do that, we need to use while loop. While loop will let the code inside it keep running until the condition is *False*.

```python
while True:
    try:
        age = int(input('How old are you? '))
        print("You are:", age)
    except ValueError:
        print("Error: Please enter a valid integer for your age. Try again.")
```

You may see that even we put the integer, it still keep asking. Why? Well because the condition is still `True`.

To make it `False` we use `break` at the end of `try`.

What if we use `break` the end of the except?

Well let's try!

```python
while True:
    try:
        age = int(input('How old are you? '))
        print("You are:", age)
        break  # Exit the loop if input is successfully converted to an integer
    except ValueError:
        print("Error: Please enter a valid integer for your age. Try again.")
        break
```

Well it's not a good idea. It also stop when we got error, so we should delete `break`.

```python
while True:
    try:
        age = int(input('How old are you? '))
        print("You are:", age)
        break  # Exit the loop if input is successfully converted to an integer
    except ValueError:
        print("Error: Please enter a valid integer for your age. Try again.")
        break #delete it later
```

## Data Types

You may notices that the vavlue of the variables can be string, number, or boolean. Yes, there are many types of data in python.

Check the following table for more info (from chatGPT)

---


| Data Type    | Description                                       | Example                      |
|--------------|---------------------------------------------------|------------------------------|
| int          | Integer values                                   | `5`, `-3`, `100`             |
| float        | Floating-point or decimal values                 | `3.14`, `-0.001`, `2.0`      |
| str          | String type for storing text                      | `'hello'`, `"world"`         |
| list         | Ordered collection of items (mutable)            | `[1, 2, 3]`, `['apple', 'banana', 'orange']` |
| tuple        | Ordered collection of items (immutable)          | `(1, 2, 3)`, `('apple', 'banana', 'orange')` |
| range        | Represents a range of numbers                    | `range(0, 10)`               |
| dict         | Collection of key-value pairs                    | `{'name': 'John', 'age': 30}` |
| set          | Unordered collection of unique items             | `{1, 2, 3}`                  |
| frozenset    | Immutable version of set                         | `frozenset({1, 2, 3})`       |
| bool         | Represents Boolean values `True` or `False`      | `True`, `False`              |
| NoneType     | Represents the absence of a value or a null value| `None`                       |
| bytes        | Represents a sequence of bytes (immutable)       | `b'hello'`, `bytes([65, 66, 67])` |
| bytearray    | Represents a mutable sequence of bytes           | `bytearray(b'hello')`        |
We are not gonna use all types of data for now. Throughout the course, you will see how the data types are used.