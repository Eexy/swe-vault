# Hash function

A **Hash function** is a [[function]] defined from a larger, possibly infinite, [[set]] of data to a smaller fixed-size set of integers

Most hash  function are modifications of **mod** functions and are defined using prime numbers to increase the chance that their values will be scattered rather than clustered together. 

In addition, making their co-domains 50% to 100% larger than their domains makes it more likely that they will be one-to-one.

In a hash function we says that two input values may **collide** when two input values have the same output value. This case is called a **collision**