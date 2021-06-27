## Data Types

### Atomic 

`int` - integers\
`float` - numbers with a decimal point\
`bool` - either `True` or `False`

### Collection 

`str` - ordered collection of characters\
`list` - ordered collection of objects

## Mutability

The ability of a type to change its state after creation.

**Mutable**: `list`, `dict`, `set`, ...\
**Immutable**: `int`, `str`, `bool`, `float`, `tuple`, ...

## str

Strings in Python are a set of chars enclosed within `'`, `"`, `'''`, or `"""`.

```python
'I\'m a string.'
"I'm a string too!"

'''
I'm a
multi
line
string.
'''

"""
I am
one
too!
"""
```

It's possible to join multiple strings using the `+` operator.
That process is called *concatenation*.

```python
first_name = 'Harry'
last_name = 'Potter'
school = 'Hogwarts'

message = 'Welcome to ' + school + ', ' + first_name + ' ' + last_name + '!'

print(message) # Welcome to Hogwarts, Harry Potter!
```

### f strings

Allow for easier access of variable values inside a string.

> f strings were introduced in Python 3.6,
> so these won't work in earlier versions of Python.

```python
message = f'Welcome to {school}, {first_name} {last_name}!'
```

Wherever a variable's value is needed inside the string,
enclose the variable's name in flower/curly braces.
No hassling around the plusses and spaces!

> Everything inside `{}` of an f string is evaluated to its str.

## list

An ordered collection of items.

```python
e = [] # empty list

avengers = [
    'Ant Man',
    'Iron Man',
    'Hulk',
    'Thor',
    'Wasp',
]

avengers[2] # 'Hulk'
avengers[7] # IndexError

avengers.append('Captain America') # adds CA to the list of Avengers
avengers.append('Spider Man')

avengers.remove('Wasp') # removes Wasp

avengers.insert(2, 'Hawk Eye') # adds Hawk Eye at index 2
```

## tuple

An ordered collection of items. The immutable version of a `list`.

```python
colors = ('RED', 'GREEN', 'BLUE')

colors[0] # 'RED'
colors[3] # IndexError
```

## dict

A collection of key value pairs, built on Hash Tables. Dicts do not preserve order,
but are fast at memberhip checks.

```python
e = {} # empty dict

ryuk = {
    'name': 'Ryuk',
    'type': 'God of Death',
    'age': 672,
}

ryuk['age'] # 672
ryuk['type'] # 'God of Death'
ryuk['fav_food'] # KeyError

ryuk['fav_food'] = 'Apple' # adds a new key 'fav_food' with the value 'Apple'
```

## set

Unordered collection of items that does not allow duplicates.
Same as `dict` except for the fact that it stores only the keys.

```python
e = set() # empty set

vowels = {'a', 'i', 'o', 'u', 'y'}
lower_case_letters = {'g', 'j', 'p', 'k', 'i', 'b', 'l', 'v', 't', 'x', 'u', 'n', 'f', 'y', 'z', 'w', 'd', 'o', 'h', 'e', 'c', 'r', 'q', 'm', 'a', 's'}

vowels.add('a') # does not change the set because 'a' already exists in the set
vowels.add('e') # adds 'e' to the set
vowels.remove('y') # removes 'y' from the set

vowels.intersection(lower_case_letters) # {'u', 'i', 'o', 'a', 'e'}
```

## Comments

Comments are a nice way to explain what your code does. These are lines of text which are ignored by the compiler and are just there for conveying the usage of certain pieces of code.<br>
They can be single-line or docstring.<br>
Single-line comments begin with `#`<br>
Docstrings begin and end with either `'''` or `"""`.
```python
# This is a single line comment
"""
This is a docstring.
It can be used as a mutliline comment too!
"""
```

## Dynamic Typing

In Python, we never have to explicitly define a variable's type.
The interpreter decides for itself based on the value assigned to the variable.

Also, variables can change types on the fly (dynamically).

## Functions, Parameters, Arguments

```python
def say_hi(name):
    print(f'Hi, {name}!')

say_hi('Genie') # Hi, Genie!
```
`say_hi` is the *function*.
`name` is its *parameter*.
`'Genie'` is the *argument*.

> To call a function, you must put `()` at the end of the function name (`func()`) and pass the required arguments (can be left empty if no arguments).
> When a function is called, the parameters are given references to the arguments.
> `name` will be bound to `'Genie'`.

## Arithmetic Operators
These operators are used to perform arithmetic operations on python objects.

Sign  | Function
:----:|---------
`+`   | add
`-`   | subtract
`*`   | multiply
`/`   | divide
`%`   | modulus
`//`  | integer divide
`**`  | raise to

## Relational Operators
These operators are used to check the relationship between two operands. They always return True or False.

Sign  | Name                  | Usage         |Function
:----:|-----------------------|---------------|--------
`==`  | Equal to              |`val1 == val2` |returns True if `val1` is equal to `val2`.
`!=`  | Not equal to          |`val1 != val2` |returns True if `val1` is not equal to `val2`.
`>`   | Greater than          |`val1 > val2`  |returns True if `val1` is greater than `val2`.
`<`   | Less than             |`val1 < val2`  |returns True if `val1` is less than `val2`. 
`>=`  | Greater than equal to |`val1 >= val2` |returns True if `val1` is greater than or equal to `val2`
`<=`  | Less than equal to    |`val1 <= val2` |returns True if `val1` is less than or equal to `val2`
`is`  | Identity operator     |`val1 is val2` |returns True if `val1` and `val2` point to same python object.
`in`  | Membership operator   |`val1 in val2` |returns True if `val1` is in the sequence `val2`.

## Logical Operators
These operators are used to combine relational expression or boolean values.

Sign  | Usage           |Function
:----:|-----------------|--------
`and` | `val1 and val2` |`val2` is only evaluated if `val1` is a true/truthy value.
`or`  | `val1 or val2`  |`val2` is only evaluaged if `val2` is a flase/falsey value.
`not` | `not val2`      | inverts the result of `val2`, if it is true/truthy, it makes it false/falsey and vice versa.

## Iterable

Any python object which can return it's member one at a time and hence allowing to be looped over is called an iterable. (str, list, dict, tuple, ...).

## Slicing

A technique that allows access to a part of an indexable type (str, list, ...).
Syntax : `iterable[start:end:step]`

```python
message = 'Hello, world!'
natural_numbers = [1, 2, 3, 4, 5, 6, 7]

message[7:12] # 'world'
message[7:] # 'world!'
message[-1] # '!'

natural_numbers[:4] # [1, 2, 3, 4]
natural_numbers[::-2] # [7, 5, 3, 1]
```

## Conditional statements

Conditional statements are way to specify conditions in your code. You might want a certain piece of code to execute only when a certain condition is met. It can be done using 
conditional statements.

```python
x = 10
y = 15
if (x > y):
    print("x is greater than y")
elif (x < y):
    print("x is smaller than y")
else:
    print("x and y are equal")
```
`if` is used to specify a condition. Condition can be any statement which returns True/Truthy/False/Falsey value.
`elif` is also used to specify a condition which will be triggered if the `if` or `elif` statements above it are not triggered.
`else` is used if none of the specified conditions are met.

## Loops

Loops are a way to repeat instruction. Python offers two types of loop. 
1. For loop - Used for running a piece of code for certain number of cycles/iterations.
2. While loop - Used for running a piece of code till a condition is True.

```python
for i in range(10):
    print(f"hi x{i}")

i = 0
while (i != 10): # brackets are optional
    print(f"hi x{i}")
    i += 1

```
`range(10)` in the above snippet is used to generate a list ( more accurately, an iterator ) of 10 elements, starting from `0`, upto `10` (exclusive).<br>
syntax: `range(start, end, step)`<br>
