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
<pre>
try: Runs the risky code that might cause an error.
except: Catches and handles the error if one occurs.
else: Executes only if no exception occurs in try.
finally: Runs regardless of what happens useful for cleanup tasks like closing files.

---
TypeError	Raised when an operation or function is applied to an object of inappropriate type (e.g., adding a string to an integer).
ValueError	Raised when a function receives an argument of the correct type but with an invalid value (e.g., converting "abc" to an integer).
ImportError	Raised when there is a problem with an import statement.
ModuleNotFoundError	Raised when a module cannot be found.
IOError	Alias for OSError (in modern Python both refer to the same base error).
FileNotFoundError	Raised when a file or directory is requested but cannot be found.
StopIteration	Raised when the next() function is called but the iterator has no more items.
KeyboardInterrupt	Raised when the user interrupts the program’s execution (e.g., pressing Ctrl+C).
SystemExit	Raised when sys.exit() is called to terminate the program.
NotImplementedError	Raised when a method that should be implemented in a subclass is not implemented.
RuntimeError	Raised when an error occurs that doesn’t fall under other categories.
RecursionError	Raised when maximum recursion depth is exceeded.
SyntaxError	Raised when there is a mistake in Python syntax.
IndentationError	Raised when indentation is not correct in Python code.
TabError	Raised when there is inconsistent use of tabs and spaces in indentation.
UnicodeError	Raised when encoding or decoding Unicode text fails.

---

