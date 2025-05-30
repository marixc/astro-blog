---
title: Perfect Numbers with Python
author: Astro Learner
description: "Find Perfect Numbers in a split second"
image:
  url: "https://docs.astro.build/default-og-image.png"
  alt: "The word astro against an illustration of planets and stars."
pubDate: 2025-05-30
tags: ["python", "math"]
---
# What are perfect numbers?
A perfect number is a number that is equal to the sum of its positive divisors. E.g.:

1 + 2 + 3 = 6

6 / 1 = 6

6 / 2 = 3

6 / 3 = 2

# The Basic Algorithm
The basic idea is to come up with an algorithm that checks whether a certain number → numis divisible by another number. Let us call that number i.


If we can divide numby iwithout a rest, we are going to add the value of ito a another variable called sum.

Regardless of whether iwas dividing numwith a rest or without, we will increment iby 1 until iis less or equal to num/2and keep adding the values of iwhere → num%i==0to sum .

If sumand numare the same we have a perfect number.
 
## Let’s implement that idea in Python:
```python
num = 2
c = 0 #counter variable that we use to keep track of how many perfect numbers we found

while c < 5: #find the first five perfect numbers
    
    sum = 0
    i = 1

    while i <= num/2:
        if(num%i==0):
            sum = sum + i
        i = i +1

    if(sum == num):
        print(num)
        c = c + 1
    num = num + 1
```


### Output
```
6
28
496
8128
```

This algorithm works fine until you want to know the 5th perfect number (33550336). We can improve the speed and efficiency with the help of Mersenne Prime & Euclid-Euler Theorem.

# Mersenne Prime & Euclid-Euler Theorem
## Mersenne Prime & Euclid-Euler Theorem
With the help of Mersenne prime numbers which are deeply interlinked with Perfect numbers, we can come up with an algorithm that is much more efficient.

Let \( k \) be a prime number:
$$
(2^k - 1)
$$

