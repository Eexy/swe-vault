---
id: binary system
aliases: []
tags: []
---
# Binary system

The **binary system** is a number system where all numbers are represented with
1 and 0

## Converting a binary to a decimal number

To convert a binary number to a decimal number we addition each 1 and 0
composing the number and multiply each of them by $2^n$ where $n$ start a 0 and
from the right

![[math/applications/binary_to_decimal.png]]

## Converting a decimal number to a binary

To convert a decimal number to a binary number we write our decoimal number as
addition of power of 2. To do that we follow this steps

1. Find the nearest power of two that is still smaller that our number
2. Substract the power of 2
3. Do the same with the remainder

![[math/applications/decimal_to_binary.png]]

## Addition of binary

To add to binary number we follow the same procedure a with decimal number
except that instead of using a carry a ten we do it a two

![[math/applications/binary_addition.png]]

## Substraction of binary

To subtract two binary numbers we follow the same procedure as we decimal but we
using 1 and 0

![[math/applications/binary_subtraction.png]]

## Two's complements and the computer representation of signed integer

In a computer all integers are represented as binary. To do that we used a fix
number of bits. 

One way to do this is to select a particular bit, normally the left-most to
indicate the sign of the integer and to use the remaining bits for its absolute
value in binary notation

The problem with this approach is that the procedures for adding the resulting
numbers are somewhat complicated and the representation of 0 is not unique

The more common approach is to use a **two's complement** which makes it
possible to add integers quite easily and results in a unique representation

In the next step we will talk about 8 bit integer but it's the same for 32, 64
bits...

The 8 bit two's complement for an integer $a$ between -128 nd 127 is the 8 bit
binary representation for :

1. a if a is greater or equal than 0
2. $2^8 - |a|$ if a is less than 0

**example** : The 8-bit representation of -46 can be found like this

1. $(2^8 - |-46|)$
2. $(256 - 46)$
2. $(128 + 64 + 16 + 2)$
2. $11010010$

We can also find the 8-bit two complement of a negative integer following those steps

1. Write the 8-bit binary representation for $|a|$
2. Switch all the 1 to 0 and all 0 to 1
3. Add 1 in binary representation

### Finding a number with a given two's complement

To find the decimal number based on a two complements we start by looking at the
left most digit. If it's a 1 the we know that the number is a negative one else
is a positive integer

Then we follow the this procedure

1. We flip all 1 to 0 and all 0 to 1
2. We convert the binary number to a decimal and we apply the negative sign if
   it's a negative number or not

### Adding / subtracting integers in two's complement form

First of all because a subtraction can be write like that

$$
a - b = a + (-b)
$$

Addition and subtraction share the same logic and in a computer the same circuit

Because we know that we can write subtraction with the form an addition we
simply do a binary addition of the two numbers

One thing to take into account is that the result must also be written in an 8
bit format. If it can't then it create an **overflow error**. Today computer can
automatically promote the result to a greater type like to promote the result to a 16 or 32
type but it depends of the computer, the program, the os...

Another thing to take into account if the result is in the correct range but we
get a carry at the end we can discard it


