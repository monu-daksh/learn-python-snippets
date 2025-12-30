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

Check type:

type(x)
```
## 📌5. Implicit Type Conversion (Automatic)
```python
Python converts types automatically.

a = 10      # int
b = 2.5     # float
c = a + b   # float

print(c)    # 12.5
print(type(c))  #<class 'float'>

Note: int → float (safe conversion)

```
## 📌6. Explicit Type Conversion (Type Casting)
```python
=> You convert manually.

x = "100"

y = int(x)
z = float(x)

print(y, z)

=> Common Casting:-

int("10")
float("3.5")
str(100)
bool(1)
list("abc")  # ['a','b','c']


❌ Invalid:
int("abc")  # ValueError
```

## 📌7. Variable Reassignment
```python

x = 10
x = x + 5
print(x)  # 15

Note: Python replaces the reference, not modifies old value
```
## 📌8. Variable Memory Behavior (Important Concept)
```python
a = 10
b = a

print(id(a))
print(id(b))

Note:Both point to same object.


=> Immutable Example (int, str, tuple)

a = 10
b = a
a = 20
print(b)  # still 10

=> Mutable Example (list)

a = [1,2]
b = a

a.append(3)
print(b)  # [1,2,3]
```

## 📌9. Constants (By Convention)
```python
=> Python has no true constants.

PI = 3.14
MAX_LIMIT = 100

Note: ⚠️ Convention only — still changeable.

```
## 📌10. Deleting Variables
```python

x = 10
del x

print(x)  # You'll get Error
```
## 📌10. None Variable
```python
=> Represents absence of value.
x = None

if x is None:
    print("No value")

```
## 📌10. Variable Unpacking
```python
a, b = (10, 20)

print(a, b)


=> Using *

a, *b = [1,2,3,4]
print(a)  # 1
print(b)  # [2,3,4]
```
## 📌11. Input Variables
```python
name = input("Enter name: ")
age = int(input("Enter age: "))

Note:⚠ input() always returns string
```


