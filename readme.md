# Dictionaries and Sets

Dictionaries are our basic **mapping** type. A mapping associates a
unique **hashable** value with some arbitrary Python object, so that we
can retrieve the object without searching if we know that value. To be
hashable, a value must be immutable and not contain any mutable objects.
Dictionaries are mutable data structures and thus can introduce aliasing
and side effect problems if you are not careful.

Since keys must be unique and can be found without searching, **sets**
are implemented as dictionaries without values in Python. As a result,
`dict` and `set` share operators and methods when it makes sense for
them to do so.

## Dictionary Creation

- Use a comma-separated list of key: value pairs within braces like
  `{'jack': 4098, 'sjoerd': 4127}` or `{4098: 'jack', 4127: 'sjoerd'}`
- Use a `dict` comprehension, like `{x: x ** 2 for x in range(10)}`
- Use the type constructor: `dict()`,
  `dict([('foo', 100), ('bar', 200)])`, `dict(foo=100, bar=200)`, etc.

## Dictionary and Set Methods

The keys, values, and (key, value) pairs stored in a dictionary can be
accessed by the following methods:

``` example
keys()
     Return a set-like object providing a view on the dict's keys

values()
     Return an object providing a view on the dict's values

items()
     Return a set-like object providing a view on the dict's items
```

These methods return a \"view\" object that dynamically changes as the
dictionary changes.

We have a handful of functions for adding or removing items from a
dictionary or set:

``` example
add(value)
    Add a value to the set

remove(value)
    Removes value from the set

update(iterable | mapping)
    Add the items in the iterable or mapping to the dict or set

clear()
    Removes all items from the dict or set

pop()
    Removes and returns a value from a set, raises KeyError if empty

pop(key[, default])
    Removes specified key from the dict and returns its value
    If key is not in the dict, returns default if specified
         or raises KeyError otherwise
```

Finally, sets specifically have a number of operators that can be
useful. The `union` and `update` functions / operators are common to
both sets and dictionaries.

    a | b (union of a and b, i.e. all elements of each)
    a & b (intersection of a and b, i.e. common elements between each)
    a - b (difference of a and b, i.e. elements of a not in b)
    a ^ b (symmetric difference of a and b, i.e. a | b - a & b)
    a <= b (a subset of b?)
    a >= b (a superset of b?)
    a |= b (update a with b)
