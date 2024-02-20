---
weight: 3
title: "Control Flow"
description: ""
icon: "article"
date: "2024-02-20T17:19:41+08:00"
lastmod: "2024-02-20T17:19:41+08:00"
draft: false
toc: true
---

Control flow is like how we make decision based *conditions*
For example, If it's sunny, we go to the park. If it's raining, we stay inside. We can also do things many times, like counting to ten or singing a song.

```python
weather= input('How is the weather today? ')

if weather == "sunny":
    print("Let's go to the park!")
else:
    print("Let's stay inside.")
```

You can see that when you type in "sunny", it will print *Let's go to the park!* but if other than *sunny* it will print Let's stay inside.

Now maybe I also want to gym if the weather is cool. We can add `else` for that.

```python
weather= input('How is the weather today? ')

if weather == "sunny":
    print("Let's go to the park!")
elif weather == "cool":
    print("Let's gym.")
else:
    print("Let's stay inside.")
```

What if have many weathers condition? Do we need to write if, elif, else like that? Yes we can

```python
weather= input('How is the weather today? ')

if weather == "sunny":
    print("Wear sunglasses and sunscreen.")
elif weather == "rainy":
    print("Bring an umbrella and wear waterproof shoes.")
elif weather == "cloudy":
    print("It might be cooler, but still bring a light jacket.")
elif weather == "snowy":
    print("Dress warmly and be cautious of slippery roads.")
else:
    print("Sorry, I don't have advice for that weather condition.")
```

But we can see that it's so repetitive. There's a function in python can do the same thing, but maybe better it called `match`

```python
weather= input('How is the weather today? ')

match weather:
    case "sunny":
        print("Wear sunglasses and sunscreen.")
    case "rainy":
        print("Bring an umbrella and wear waterproof shoes.")
    case "cloudy":
        print("It might be cooler, but still bring a light jacket.")
    case "snowy":
        print("Dress warmly and be cautious of slippery roads.")
    case _:
        print("Sorry, I don't have advice for that weather condition.")
```

Alright, it seems we learn something new.

## while loops

Ok now the previous example we see that it will stop when we give the input. Now we want to keep asking until we don't need it anymore. let's use `while`

```python
while True:
  weather= input('How is the weather today? ')

  match weather:
    case "sunny":
        print("Wear sunglasses and sunscreen.")
    case "rainy":
        print("Bring an umbrella and wear waterproof shoes.")
    case "cloudy":
        print("It might be cooler, but still bring a light jacket.")
    case "snowy":
        print("Dress warmly and be cautious of slippery roads.")
    case _:
        print("Sorry, I don't have advice for that weather condition.")
```

Yes we can see that it keep looping, but the problem it does not know when to stop. As we know it can stop only when `while` not `True` anymore. Before we use `break` to stop it right?

So how can we use it this time to stop? Maybe when the input is `exit` ? Let's try it.

```python
while True:
  weather= input('How is the weather today? (type "exit" to stop!)')

  match weather:
    case "exit":
      print('exit')
      break
    case "sunny":
        print("Wear sunglasses and sunscreen.")
    case "rainy":
        print("Bring an umbrella and wear waterproof shoes.")
    case "cloudy":
        print("It might be cooler, but still bring a light jacket.")
    case "snowy":
        print("Dress warmly and be cautious of slippery roads.")
    case _:
        print("Sorry, I don't have advice for that weather condition.")
```

There's another way to achieve the same goal and it seperate the `match` and `exit`.

```python
while True:
    weather = input('How is the weather today? (Type "exit" to quit) ')

    if weather ==  "exit":
        print("Exiting...")
        break

    match weather:
        case "sunny":
            print("Wear sunglasses and sunscreen.")
        case "rainy":
            print("Bring an umbrella and wear waterproof shoes.")
        case "cloudy":
            print("It might be cooler, but still bring a light jacket.")
        case "snowy":
            print("Dress warmly and be cautious of slippery roads.")
        case _:
            print("Sorry, I don't have advice for that weather condition.")
```

Yes it work now!
You can make it work even the user using CAPITAL LETTER by using `lower()`


```python
    weather = input('How is the weather today? (Type "exit" to quit) ').lower()
```

It like conver ALL CAPS => all caps. Before it compared with the conditions.

```python
while True:
    weather = input('How is the weather today? (Type "exit" to quit) ').lower()


    if weather ==  "exit":
        print("Exiting...")
        break

    match weather:
        case "sunny":
            print("Wear sunglasses and sunscreen.")
        case "rainy":
            print("Bring an umbrella and wear waterproof shoes.")
        case "cloudy":
            print("It might be cooler, but still bring a light jacket.")
        case "snowy":
            print("Dress warmly and be cautious of slippery roads.")
        case _:
            print("Sorry, I don't have advice for that weather condition.")
```

## for loop

Later on we will back learn more about for loop. But now just understand for loop you can set how many you want to repeat.

```python
num_iterations = 3

for i in range(num_iterations):
  print(i)
```