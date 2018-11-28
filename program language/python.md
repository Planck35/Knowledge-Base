###Python iterator
Technically, in Python, an iterator is an object which implements the iterator protocol, which consist of the methods `__iter__()` and `__next__()`

####Iterator vs Iterable
Lists, tuples, dictionaries, and sets are all iterable objects. They are iterable containers which you can get an iterator from.

All these objects have a `iter()` method which is used to get an iterator:

Even strings are **iterable** objects, and can return an iterator:

```Python
mystr = "banana"
myit = iter(mystr)

print(next(myit))
print(next(myit))
```
####Looping Through an Iterator
We can also use a for loop to iterate through an iterable object:
```Python
mytuple = ("apple", "banana", "cherry")

for x in mytuple:
  print(x)
```
The `for` loop actually creates in iterator object and executes the `next()` method for each loop.

####Create an Iterator
To create an object/class as an iterator you have to implement the methods `__iter__()` and `__next__()` to your object.

All classes that have a function called `__init__()`, which allows you do some initializing when the object is being created.

The `__iter__()` method acts similar, you can do operations (initializing etc.), but must always return the iterator object itself.

The `__next__()` method also allows you to do operations, and must return the next item in the sequence.

```Python
class MyNumbers:
  def __iter__(self):
    self.a = 1
    return self

  def __next__(self):
    x = self.a
    self.a += 1
    return x
```

####StopIteration
The example above would continue forever if you had enough `next()` statements, or if it was used in a for loop.

To prevent the iteration to go on forever, we can use the `StopIteration` statement.

In the `__next__()` method, we can add a terminating condition to raise an error if the iteration is done a specified number of times:

####Unpacking Argument Lists
When the arguments are already in a list or tuple but need to be unpacked for a function call requiring separate positional arguments. 
For instance, the built-in `range()` function expects separate start and stop arguments. If they are not available separately, write the function call with the `*`-operator to unpack the arguments out of a list or tuple
```Python
>>> list(range(3, 6))            # normal call with separate arguments
[3, 4, 5]
>>> args = [3, 6]
>>> list(range(*args))            # call with arguments unpacked from a list
[3, 4, 5]
```
In the same fashion, dictionaries can deliver keyword arguments with the `**`-operator:
```Python
>>> def parrot(voltage, state='a stiff', action='voom'):
...     print("-- This parrot wouldn't", action, end=' ')
...     print("if you put", voltage, "volts through it.", end=' ')
...     print("E's", state, "!")
...
>>> d = {"voltage": "four million", "state": "bleedin' demised", "action": "VOOM"}
>>> parrot(**d)
-- This parrot wouldn't VOOM if you put four million volts through it. E's bleedin' demised !
```