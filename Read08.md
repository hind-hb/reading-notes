# Read08 : List Comprehensions in Python

We can use comprehensions to handle lists in a more concise manner than a loop/conditional.

## Syntax

my_new_list = [ *expression* for *item* in *list* ]

An example would be creating a list of digits using range.

```Python
digits = [x for x in range(10)]
```

Prints: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

We can use comprehensions to create more complicated functions on a list of objects very readily. In addition, we can also add additional filters in a very short line of code. 

Example:

```Python
even_numbers = [ x for x in range(1, 20) if x % 2 == 0]
```

This line of code prints all even numbers in the range.

A bunch of examples of we can do with a list comprehension:

- multiply elements in a list
- show the first letter of a list of words
- separate all the characters in a string
- change a letter's case
- take only digits from string data

We can also add our own custom functions into a list comprehension.
Example:

```Python
# list comprehension with functions
# create a function that returns a number doubled
def double(x):
    return x*2

nums = [double(x) for x in range(1,10)]
print(nums)

# add a filter so we only double even numbers
even_nums = [double(x) for x in range(1,10) if x%2 == 0]
print(even_nums)
```

In this code, we see that a double(x) function is created to double its parameter. When that function is invoked in the comprehension, it doubles all of the even numbers in the list.

>Learning to make use of advanced features like list comprehension will save time and improve productivity.
>Not only will your colleagues thank you when your Python code is more concise and easier to read, but you’ll thank yourself when you come back to a program you haven’t worked on in months and the code is manageable.

