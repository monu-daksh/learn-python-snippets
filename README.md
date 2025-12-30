# 🐍 Learn Python with Code Snippets

This repo contains my **Python learning journey** with **code snippets, examples, and notes**.  
If you are a beginner and want a **Python cheatsheet** or **ready-to-use examples**, this repo is for you 🚀  

## 📂 Topics Covered
- Basics: Variables, Data Types, Loops, Functions
- Intermediate: OOP, File Handling, Exceptions
- Advanced: Decorators, Generators, Async/Await
- Mini Projects: Calculator, To-do App, Games

---

## 📌1. Variables in Python (Data Holders)
```python
=> How to Write Variables

name = "John"
age = 25
is_active = True

print(name, age, is_active)

=> Multiple Assignment

a, b, c = 10, 20, 30
print(a, b, c)

=> Same Value to Multiple Variables

x = y = z = 100
print(x)
print(y)
print(z)

```
## 📌2. Variable Naming Rules
```python
✅ Allowed:

user_name = "Monu"
_age = 26
totalAmount = 500


❌ Not Allowed:

1name = "Monu"   # cannot start with number
user-name = "x"  # hyphen not allowed
class = 10       # reserved keyword


Best Practices (Pythonic)

snake_case = "recommended"
camelCase = "allowed but not preferred"
UPPER_CASE = "constant"
```
## 📌3. Types of Variables (Based on Scope)
```python

🔹 Local Variable
Declared inside a function.

def test():
    x = 10  # local variable, which is available inside function!
    print(x)

test()
print(x)  # Error: Not available outside of function


🔹 Global Variable
Declared outside functions.

x = 10

def show():
    print(f"available inside function", x)
    
show()
print(f"available outside function", x)


🔹 Global Keyword
Modify global variable inside function.

count = 10

def increment():
    global count
    count+=1
    
increment()
print(count)  # global variable is updated!


🔹 Nonlocal Variable (Nested Functions)

def outer():
    x = 10            # x is created inside outer
    def inner():
        nonlocal x    # use the x from outer (not a new one)
        x += 5        # increase that x by 5
    inner()           # run inner, so x becomes 15
    print(x)          # print 15

outer()

```
## 📌4. Variable Types (Data Types)
```python
Python is dynamically typed.

x = 10        # int
x = "hello"  # now string


Common Types:


# int -> Whole number (no decimal)
x_int = 10        # Example: 10

# float -> Number with decimal point
x_float = 10.5    # Example: 10.5

# str -> Text or sequence of characters
x_str = "hello"   # Example: "hello"

# bool -> True or False (used for conditions)
x_bool_true = True    # Example: True
x_bool_false = False  # Example: False

# list -> Ordered collection, can change (mutable)
# Ordered means items keep the same sequence you added them.
# You can access by index: x_list[0] -> 1
x_list = [1, 2, 3]    # Example: [1, 2, 3]

# tuple -> Ordered collection, cannot change (immutable)
# Ordered like list, but you cannot modify after creation.
x_tuple = (1, 2)      # Example: (1, 2)

# dict -> Key-value pairs (like a map)
# Conceptually unordered (you access by key, not position).
# In Python 3.7+, insertion order is preserved internally, but still use keys.
x_dict = {"a": 1}     # Example: {"a": 1}

# set -> Unordered collection of unique items
# Unordered means no fixed position; cannot access by index.
# Items may appear in any order when printed.
x_set = {1, 2}        # Example: {1, 2}

# NoneType -> Represents "nothing" or "no value"
x_none = None         # Example: None

```
