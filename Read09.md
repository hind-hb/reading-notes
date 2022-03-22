# Read: 09 - Readings: Dunder Methods & Statistics - Probability

## Dunder Techniques

Special methods are a set of predefined methods in Python that you can use to enhance your classes. They can be easily identified since they begin and conclude with double underscores, such as init or str.

In Python, these "dunders" or "special methods" are sometimes known as "magic methods." However, adopting this phrase can make things appear more sophisticated than they are—at the end of the day, they aren't "magical."

You can use Dunder methods to mimic the behavior of built-in types. You can call len('string') to retrieve the length of a string, for example.

Slicing is another example. You can leverage Python's list slicing syntax by implementing a getitem method: obj[start:stop].

The Account class is used to create account instances.

# For Example

__repr__: string representation of an object. This is how you would make an object of the class. The goal of __repr__ is to be unambiguous.

__str__:string representation of an object. This is for the enduser.

nums = [1, 2, 3, 4, 5]

print(len(nums)) #5

print(nums.__len__()) #5

## Probability (statistics)

Probability aims to answer the question, "What is the probability of an event occurring?" at its most fundamental level. 

An interesting conclusion is referred to as an event. We must also include all other possible events when calculating the probability of an event occurring. 

The simple coin toss is the quintessential example of probability. Only the following outcomes are possible in a coin toss:

We'll obtain our data by flipping a coin ten times and counting how many heads we get. 

A trial is defined as a series of ten coin flips. The number of heads we notice will be our data point. 

We might not receive the "perfect" five heads, but that's not a big concern because we'll be fine.
