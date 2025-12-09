<pre>
Numeric: int, float, complex
Sequence Type: string, list, tuple
Mapping Type: dict
Boolean: bool
Set Type: set, frozenset
Binary Types: bytes, bytearray, memoryview

---

Walrus Operator Syntax
variable := expression
The expression on the right-hand side is evaluated, assigned to the variable, and then returned.

---

Match-Case Statement
match-case statement is Python's version of a switch-case found in other languages. It allows us to match a variable's value against a set of patterns.

number = 2
​
match number:
    case 1:
        print("One")
    case 2 | 3:
        print("Two or Three")
    case _:
        print("Other number")
Output:
Two or Three

---

Using Else with Loops in Python
The else block just after for/while is executed only when the loop is NOT terminated by a break statement.

---

def cube(x): return x*x*x   # without lambda
cube_l = lambda x : x*x*x  # with lambda

---
Note: Technically, Python uses "pass-by-object-reference". Mutable objects behave like pass by reference, while immutable objects behave like pass by value

---

*args: Non-keyword (positional) arguments
**kwargs: Keyword arguments, arguments are collected into a dictionary
def fun(*args):
    return sum(args)
def fun(**kwargs):
    for k, val in kwargs.items():
        print(k, val)
</pre>       
---
Converting map object to a list: By default, map() function returns a map object, which is an iterator. In many cases, we will need to convert this iterator to a list to work with the results directly.

---
filter() in python: filter() function is used to extract elements from an iterable (like a list, tuple or set) that satisfy a given condition. It works by applying a function to each element and keeping only those for which function returns True.

---
<pre>
a = [1, 2, 3, 4, 5, 6]
b = filter(lambda x: x % 2 == 0, a)
c = map(lambda x: x * 2, b)
filter(lambda x: x % 2 == 0, a): Selects only even numbers from the list ([2, 4, 6]).
map(lambda x: x * 2, b): Doubles each of the filtered even numbers ([4, 8, 12]).
</pre>
---
reduce() in Python: reduce() function (from functools) applies a function cumulatively to an iterable, reducing it to a single value. It’s handy for concise tasks like summing, multiplying (factorial), finding max/min, concatenating strings or flattening lists. Use it for simple one-line reductions, avoid it for complex logic (loops are clearer) or when intermediate results are needed.
```
from functools import reduce
li = ["Geeks", "for", "Geeks"]
res = reduce(lambda x, y: x + " " + y, li)
print(res)
```
reduce(lambda x, y: x + " " + y, words) takes two strings at a time and concatenates them with a space.
"Geeks" + "for" -> "Geeks for", then "Geeks for" + "Geeks" -> "Geeks for Geeks".

---
The accumulate() function (from itertools) and reduce() both apply a function cumulatively to items in a sequence. However, accumulate() returns an iterator of intermediate results, while reduce() returns only final value.

---
In Python, decorators are flexible way to modify or extend behavior of functions or methods, without changing their actual code.
```
def decorator(func):
    def wrapper():
        print("Before calling the function.")
        func()
        print("After calling the function.")
    return wrapper

@decorator # Applying the decorator to a function
def greet():
    print("Hello, World!")
greet()
```
<pre>
Before calling the function.
Hello, World!
After calling the function.
</pre>
---
The most frequently used built-in decorators are @staticmethod, @classmethod and @property.

---
