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
## 📌12. Boolean Nature of Variables
```python
bool(0)      # False
bool("")     # False
bool([])     # False
bool(None)   # False

bool(1)      # True
bool("a")    # True
```
## 📌13. Variable Shadowing
```python
x = 10

def test():
    # This inner x hides (or covers) the outer x when you are inside the function.
    # when you do print(x) inside test(), Python uses the inner x (5), not the global one (10).
    x = 5  # shadows global x
    print(x)

test()
print(x)
```
## 📌14. Dynamic Nature of Python Variables
```python
x = 10
x = "Python"
x = [1,2,3]

Note: No type declaration required.
```
## 📌15. Checking Variable Existence
```python

if "x" in globals():
    print("x exists")
else:
    print("Not exists")
```
## 📌16. Strings in Python (VERY IMPORTANT)
```python
=> Creating Strings

s1 = 'Hello'
s2 = "Hello"
s3 = '''Hello
World'''
s4 = """Multi
Line"""

Note:
✔ All are valid
✔ Triple quotes support multiline strings

```
## 📌17. String is Immutable (CRITICAL CONCEPT)
```python

s = "hello"
s[0] = "H"

print(s) # Error

Note:
✔ You cannot modify a string
✔ You must create a new string

s = "hello"
s = "H" + s[1:]
print(s)  # Hello
```
## 📌18. String Indexing
```python

=> Positive Index

s = "python"
print(s[0])  # at index 0 => p
print(s[3])  #  at index 3 => h

Negative Index
print(s[-1])  # n
print(s[-2])  # o

=> How Indexes works in python/javascript

s = "python"
Indexes:  p   y   t   h   o   n
Positive: 0   1   2   3   4   5
Negative:-6  -5  -4  -3  -2  -1
```
## 📌19. String Slicing
```python

s = "Python"
s[start : end : step]

# - start: where to begin (inclusive)
# - end:   where to stop (exclusive) — it stops just BEFORE this index
# - step:  how to move (default is 1). Use negative step to go backwards.


s = "Python"

print(s[0:4])     # 'Pyth'
# From index 0 (P) up to index 4 (not included) -> P(0), y(1), t(2), h(3)

print(s[:4])      # 'Pyth'
# Start is omitted -> defaults to 0
# So it’s the same as s[0:4]

print(s[2:])      # 'thon'
# End is omitted -> goes till the end
# Starts at index 2 (t) -> t(2), h(3), o(4), n(5)

print(s[::2])     # 'Pto'
# Full slice but step=2 -> take every 2nd character from start
# Picks: P(0), t(2), o(4)

print(s[::-1])    # 'nohtyP'
# step=-1 -> go backwards (reverse the string)
# Starts at the end and moves left: n, o, h, t, y, P

```

## 📌20. Length of String
```python
s = "python
len(s)  # 6

```
## 📌21. String Concatenation
```python
a = "Hello"
b = "World"

print(a + " " + b)

=> Using *
print("Hi " * 3)
```
## 📌22. String Membership
```python
"Py" in "Python"      # True
"x" not in "Python"   # True

=> String Comparison

"a" < "b"      # True
"apple" > "app"

Note: Based on ASCII / Unicode values
```

## 📌23. Case Conversion
```python

s = "PyThOn"

s.lower()      # 'python'
# Converts ALL letters to lowercase.
# PyThOn -> python

s.upper()      # 'PYTHON'
# Converts ALL letters to uppercase.
# PyThOn -> PYTHON

s.title()      # 'Python'
# Makes the first letter uppercase and the rest lowercase.
# PyThOn -> Python

s.capitalize() # 'Python'
# Capitalizes ONLY the first character and makes the rest lowercase.
# PyThOn -> Python

s.swapcase()   # 'pYtHoN'
# Swaps the case of each letter.
# Uppercase becomes lowercase, lowercase becomes uppercase.
# PyThOn -> pYtHoN

```
## 📌24. Whitespace Handling
```python

# There are spaces before and after the word "hello"
s = "  hello  "


s = "  hello  "   # There are spaces before and after the word "hello"

s.strip()      # "hello"
# Removes spaces from BOTH ends (left and right).
# So "  hello  " becomes "hello".

s.lstrip()     # "hello  "
# Removes spaces ONLY from the LEFT side.
# So "  hello  " becomes "hello  " (right spaces remain).

s.rstrip()     # "  hello"
# Removes spaces ONLY from the RIGHT side.
# So "  hello  " becomes "  hello" (left spaces remain).

```
## 📌25. Finding & Searching
```python
s = "hello world"

# find() -> Finds the FIRST occurrence of the substring.
# Returns the index (0-based). If NOT found, returns -1.

# NOTE: It is CASE-SENSITIVE.
print(s.find("o"))   # 4  (first 'o' at index 4)
print(s.find("O"))   # -1 (uppercase 'O' not found)

# rfind() -> Finds the LAST occurrence of the substring.
# Returns the index. If NOT found, returns -1.

# Also CASE-SENSITIVE.
print(s.rfind("o"))  # 7  (last 'o' at index 7)
print(s.rfind("O"))  # -1 (not found)

# index() -> Same as find(), but if NOT found, raises ValueError.
# CASE-SENSITIVE.
print(s.index("o"))  # 4
# print(s.index("O")) #  ValueError: substring not found

# count() -> Counts HOW MANY times the substring appears.
# Returns 0 if NOT found. CASE-SENSITIVE.
print(s.count("o"))  # 2
print(s.count("O"))  # 0
```
## 📌26. Splitting & Joining
```python

s = "a,b,c"
s.split(",")   # ['a', 'b', 'c']

"-".join(["a", "b", "c"])

```
## 📌27. Checking Content (Very Important)
```python

s = "Python123"

s.isalpha()     # False
# Checks if ALL characters are letters (A-Z or a-z).
# "Python123" has numbers, so result is False.

s.isdigit()     # False
# Checks if ALL characters are digits (0-9).
# "Python123" has letters, so result is False.

s.isalnum()     # True
# Checks if ALL characters are letters OR digits (no spaces or symbols).
# "Python123" has letters and digits only, so True.

s.islower()     # False
# Checks if ALL letters are lowercase.
# "Python123" has uppercase 'P', so False.

s.isupper()     # False
# Checks if ALL letters are uppercase.
# "Python123" has lowercase letters, so False.

s.isspace()     # False
# Checks if ALL characters are whitespace (spaces, tabs, newlines).
# "Python123" has no spaces, so False.

s.startswith("Py")  # True
# Checks if the string starts with "Py".
# "Python123" starts with "Py", so True.

s.endswith("on")    # False
# Checks if the string ends with "on".
# "Python123" ends with "123", so False.

```
## 📌28. String Formatting (VERY IMPORTANT)
```python
name = "Monu"
age = 26

print(f"My name is {name} and age is {age}")
```

## 📌29. Iterating Over String
```python
s = "python"

for ch in s:
  print(ch)

=> With index:

for i in range(len(s)):
    print(i, s[i])

```
## 📌30. String to List & List to String
```python

=> String to List

s = "abc"
lst = list(s)
print(lst)  
# Output: ['a', 'b', 'c']
# Explanation: list() takes each character from the string and makes a list of characters.

=> List to String

chars = ['a', 'b', 'c']
joined = "".join(chars)
print(joined)  
# Output: 'abc'
# Explanation: join() combines all items in the list into one string.
# The string before .join() is the separator. Here it's "", so no extra characters are added.

```
## 📌31. ASCII / Unicode
```python

# ord() and chr() are built-in functions in Python.

# ord(character) -> gives the Unicode code point (integer) of the character.
print(ord("A"))   # 65
# Explanation:
# "A" is a character.
# ord("A") returns 65 because in ASCII/Unicode, 'A' corresponds to code point 65.

# chr(number) -> gives the character for the given Unicode code point.
print(chr(65))    # 'A'
# Explanation:
# 65 is an integer code point.
# chr(65) returns 'A' because 65 maps to 'A' in Unicode.

# Works for other characters too:
print(ord("a"))   # 97
print(chr(97))    # 'a'

# Unicode example:
print(ord("₹"))   # 8377 (Indian Rupee symbol)
print(chr(8377))  # '₹'
```

## 📌32. String Memory Behavior
```python

a = "hello"
b = "hello"

print(id(a) == id(b))  # True

# Explanation:
# id() gives the memory address (identity) of an object.
# In Python, small strings and some immutable objects are "interned".
# Interning means Python stores one copy of the same string to save memory.
# So both a and b point to the SAME string object in memory.
# Therefore, id(a) == id(b) is True.
```
## 📌33. Common String Problems (Logic)
```python

# 1) Reverse a string
s = "Python"
print(s[::-1])       # 'nohtyP'
# Explanation:
# s[start:end:step]
# step = -1 means "go backwards", so this reverses the whole string.

# 2) Remove spaces from a string
s = "p y t h o n"
print(s.replace(" ", ""))   # 'python'
# Explanation:
# replace(" ", "") removes all SPACE characters.
# Note: It removes only plain spaces, not tabs or newlines.

# If you want to remove ALL kinds of whitespace (space, tab, newline), use:
t = "p\t y\n t  h o n"
print("".join(t.split()))   # 'python'
# Explanation:
# split() with no separator splits on ANY whitespace and removes them.
# join() with "" glues the parts back together without spaces.

# 3) Check if a substring exists (case-insensitive)
s = "Hello PyThoN World"
if "py" in s.lower():
    print("Found 'py'")   # Found 'py'
# Explanation:
# s.lower() makes the string lowercase, so case doesn’t matter.
# "py" in ... checks if "py" exists anywhere in the string.

```

## 📌34. Performance Tip
```python
❌ Bad:

s = ""
for i in range(1000):
    s += str(i)

✅ Good:
parts = []
for i in range(1000):
    parts.append(str(i))

s = "".join(parts)
```
## 📌35. String Functions (Built-in)
```python

len()
max()
min()
sorted()

sorted("python")  # ['h','n','o','p','t','y']
```
## 📌36. Arithmetic Operators
```python
=> Addition (+)

a = 10
b = 5
print(a + b)


=> Subtraction (-)

a = 10
b = 5
print(a - b)

=> Multiplication (*)

a = 10
b = 5
print(a * b)

=> Division (/)

a = 10
b = 5
print(a / b)

=> Floor Division (//)

a = 10
b = 3

print(a // b)   # 3
# Explanation:
# 10 ÷ 3 = 3.333...
# Floor division removes the decimal part and rounds DOWN → 3

=> Modulus (%)

print(10 % 3)  # Output: 1

# The % operator gives the remainder after division
# Here: 10 divided by 3 leaves a remainder 1


print(7 % 2)    # 1  -> 7 = 2*3 + 1 (odd numbers give remainder 1 when % 2)
print(8 % 2)    # 0  -> 8 = 2*4 + 0 (even numbers give remainder 0 when % 2)
print(14 % 5)   # 4  -> 14 = 5*2 + 4
print(3 % 10)   # 3  -> When the first number is smaller, remainder is the first number

=> Power (**)

a = 2
b = 4
print(a ** b)  # 16

=> Assignment Operators

x = 10
print(x)

=> += (add and assign)

x = 10            # start with 10
x += 5            # add 5 to x
# Equivalent: x = x + 5
print(x)          # 15

=> -= (subtract and assign)

x = 10            # start with 10
x -= 3            # subtract 3 from x
# Equivalent: x = x - 3
print(x)          # 7

=> *= (multiply and assign)

x = 4             # start with 4
x *= 3            # multiply x by 3
# Equivalent: x = x * 3
print(x)          # 12

=> /= (divide and assign — true division, result is float)

x = 10            # start with 10
x /= 2            # divide x by 2
# Equivalent: x = x / 2
print(x)          # 5.0  (note: division makes it a float)

=> //= (floor divide and assign — integer-like division)

x = 10            # start with 10
x //= 3           # floor divide (drops the decimal part)
# Equivalent: x = x // 3
print(x)          # 3     (because 10 / 3 is 3.333..., floor is 3)

=> %= (modulus and assign — remainder)

x = 10            # start with 10
x %= 4            # store the remainder of x divided by 4
# Equivalent: x = x % 4
print(x)          # 2     (since 10 = 4*2 + 2, remainder is 2)

=> **= (power and assign — exponent)

x = 2             # start with 2
x **= 3           # raise x to the power of 3
# Equivalent: x = x ** 3
print(x)          # 8     (2^3 = 8)
```
## 📌37. Comparison Operators (Boolean Output)
```python

# Equal to (==): checks if values are the same
print(5 == 5)      # True
print(5 == 7)      # False

# Not equal (!=): checks if values are different
print(5 != 7)      # True
print(5 != 5)      # False

# Greater than (>): left side is bigger than right side?
print(10 > 3)      # True
print(3 > 10)      # False

# Less than (<): left side is smaller than right side?
print(3 < 10)      # True
print(10 < 3)      # False

# Greater than or equal to (>=): bigger OR equal
print(5 >= 5)      # True
print(5 >= 6)      # False

# Less than or equal to (<=): smaller OR equal
print(4 <= 4)      # True
print(4 <= 3)      # False

```
## 📌38. Comparison Operators (Boolean Output)
```python
#1:--> Basic number comparisons

# Equal to (==): checks if values are the same
print(5 == 5)      # True
print(5 == 7)      # False

# Not equal (!=): checks if values are different
print(5 != 7)      # True
print(5 != 5)      # False

# Greater than (>): left side is bigger than right side?
print(10 > 3)      # True
print(3 > 10)      # False

# Less than (<): left side is smaller than right side?
print(3 < 10)      # True
print(10 < 3)      # False

# Greater than or equal to (>=): bigger OR equal
print(5 >= 5)      # True
print(5 >= 6)      # False

# Less than or equal to (<=): smaller OR equal
print(4 <= 4)      # True
print(4 <= 3)      # False


# 2:--> Comparisons with variables


x = 10
y = 7

print(x > y)       # True, because 10 is greater than 7
print(x == y)      # False, because 10 is not equal to 7
print((x - y) >= 3)  # True, because 10 - 7 = 3, and 3 >= 3


# 3:-> String comparisons (lexicographic order)
# Python compares the Unicode (ASCII for English letters) value of each character

print("Apple" == "Apple")   # True
# Both strings are exactly the same.
# Same characters, same order, same case → values match completely.


print("Apple" == "apple")   # False
# 'A' (uppercase) and 'a' (lowercase) have different Unicode values.
# Case matters in string comparison, so they are NOT equal.


print("abc" < "abd")        # True
# Comparison happens character by character:
# 'a' == 'a' → move to next
# 'b' == 'b' → move to next
# 'c' < 'd' → True, so entire string comparison becomes True


print("Banana" > "Apple")   # True
# First characters are compared:
# 'B' vs 'A'
# Unicode value of 'B' is greater than 'A'
# So "Banana" is considered greater than "Apple"


print("a" > "Z")            # True
# Unicode value of lowercase letters is greater than uppercase letters
# 'Z' → Unicode 90
# 'a' → Unicode 97
# Since 97 > 90, 'a' is greater than 'Z'


# 4:->  Comparing lengths or mixed expressions

name = "Monu"
print(len(name) > 3)    # True (length is 4)

a = 5
b = 2
print(a * b == 10)      # True (because 5 * 2 = 10)


# 5:-> Comparisons with lists and tuples
# Lists and tuples are compared element-by-element (left to right)

print([1, 2, 3] == [1, 2, 3])   # True
# Both lists have the same elements
# Same values, same order → lists are equal

print([1, 2, 3] == [1, 2, 4])   # False
# Comparison starts from index 0:
# 1 == 1 → OK
# 2 == 2 → OK
# 3 != 4 → mismatch found → result is False

print([1, 2, 3] == [3, 2, 1])   # False
# Order matters in lists
# Even though values are same, positions are different
# Python checks exact sequence, not just values

# Tuples follow the same comparison rules as lists
print((1, 2) < (1, 3))          # True
# Step-by-step comparison:
# First element: 1 == 1 → move to next
# Second element: 2 < 3 → True
# So entire tuple comparison becomes True

Note: Python compares lists and tuples from left to right, one element at a time, and stops at the first difference.

# 6:-> Boolean results and usage in if statements
# Boolean values (True / False)

age = 18

is_adult = age >= 18     # Comparison operator returns a Boolean (True or False)
# age >= 18 → True because 18 is equal to 18

print(is_adult)         # True

Note: Every comparison in Python results in a Boolean and Boolean values are: True and False.

# Using Boolean in if statement

if is_adult:
    print("You are an adult.")
else:
    print("You are a minor.")


# Direct condition inside if

age = 16

if age >= 18:
    print("Adult")
else:
    print("Minor")

# if - elif - else (Multiple conditions)

marks = 72

if marks >= 90:
    print("Grade A")
elif marks >= 75:
    print("Grade B")
elif marks >= 60:
    print("Grade C")
else:
    print("Fail")

# 7:-> Chaining comparisons (Python feature)

age = 25

print(18 <= age <= 60)   # True
# Python checks this as:
# 18 <= age AND age <= 60
# Both conditions are True → final result is True


# Invalid vs valid age check
age = 15

print(0 <= age <= 120)   # True
# Checks:
# 0 <= age → True
# age <= 120 → True
# Age lies within valid human range


# Marks between two values
marks = 72

if 60 <= marks < 75:
    print("Grade C")
# First: 60 <= marks → True
# Second: marks < 75 → True
# Both True → condition passes


# Decimal values comparison
temperature = 36.5

print(36.0 <= temperature <= 37.5)   # True
# Works same for float values
# Checks if temperature lies in healthy range


# Chaining with variables (step-by-step logic)
a = 5
b = 10
c = 15

print(a < b < c)   # True
# Python evaluates:
# a < b → True
# b < c → True
# All comparisons must be True


# Chaining with equality and comparison
x = 10

print(5 < x == 10)   # True
# Evaluated as:
# 5 < x AND x == 10
# Both conditions are True

# Chaining with strings (lexicographical order)
print("apple" < "banana" < "carrot")   # True
# String comparison happens alphabetically
# "apple" < "banana" and "banana" < "carrot"

# Chaining with characters (Unicode values)
print("A" < "M" < "Z")   # True
# Characters are compared using Unicode values


# What Python DOES NOT do (Important Interview Point)
x = 5

print(x > 3 > 1)   # True
# Evaluated as:
# x > 3 AND 3 > 1
# NOT as: (x > 3) > 1


# Comparing with None (special value meaning “no value”)

value = None
# None represents the absence of a value (nothing / no data)

# Use 'is' to compare with None (BEST PRACTICE)
print(value is None)       # True
# 'is' checks identity (same object in memory)
# value points to the single None object → True

print(value is not None)   # False
# value IS None, so it is NOT "not None" → False


print(None == 0)      # False
# None is not equal to 0
# 0 means numeric zero, None means "no value"
# They represent completely different concepts

print(None == "")     # False
# Empty string "" still has a value (length 0)
# None means no value at all → not equal

print(None == [])     # False
# Empty list [] is still a list object
# None is not a container → not equal

# Equality vs Identity (== vs is) — simple demo

# '==' checks VALUE equality
# It compares the contents of objects (what is inside)

# 'is' checks IDENTITY
# It checks whether both variables point to the SAME object in memory

a = [1, 2, 3]   # A new list object is created in memory
b = [1, 2, 3]   # Another new list object is created (different from 'a')
c = a           # 'c' does NOT create a new list
                # It points to the SAME list object as 'a'

print(a == b)   # True
# Both lists contain the same elements in the same order
# Value comparison → contents are equal

print(a is b)   # False
# 'a' and 'b' are two different list objects in memory
# Even though values are same, memory locations are different

print(a is c)   # True
# 'c' and 'a' refer to the SAME object
# Both names point to the same memory location


Note: Simple Mental Model (Very Important)
== → “Do they look the same?”
is → “Are they the same thing?”

```

## 📌39. Loops in Python (Complete Guide)
```python
# 1:---> for loop (Most used loop)
# Example 1: Loop through a list

fruits = ["apple", "banana", "mango"]

for fruit in fruits:
    print(fruit)
    # Python takes one item at a time from the list
    # 'fruit' gets the current item

# Example 2: Using range()

for i in range(5):
    print(i)
    # range(5) gives numbers from 0 to 4
    # loop runs 5 times


# Example 3: Start, stop, step
for i in range(2, 10, 2):
    print(i)
    # Starts from 2
    # Stops before 10
    # Jumps by 2 each time

# Example 4: Loop through string
name = "Python"

for char in name:
    print(char)
    # Each character is processed one by one

# Example 5: Loop through dictionary
student = {"name": "Monu", "age": 22}

for key in student:
    print(key, student[key])
    # 'key' gets dictionary keys
    # student[key] gives the value

# 2:---> while loop (Condition-based loop)
# Example 1: Basic while loop

count = 1

while count <= 5:
    print(count)
    count += 1
    # Loop runs while condition is True
    # count increases each time


# Example 2: Infinite loop (with break)

i = 1

while True:
    print(i)
    if i == 3:
        break
    i += 1
    # break stops the loop

# break (Stop the loop)
for i in range(10):
    if i == 5:
        break
    print(i)
    # Loop stops completely when i == 5


# continue (Skip current iteration)
for i in range(5):
    if i == 2:
        continue
    print(i)
    # Skips printing when i == 2

# else with loops
for i in range(3):
    print(i)
else:
    print("Loop finished normally")
    # else runs only if loop did NOT break

# while-else
i = 0

while i < 3:
    print(i)
    i += 1
else:
    print("While loop ended")


# Nested loops (Loop inside loop)
for i in range(3):
    for j in range(2):
        print(i, j)
        # Inner loop runs fully for each outer loop iteration

# Looping with enumerate()
fruits = ["apple", "banana", "mango"]

for index, fruit in enumerate(fruits):
    print(index, fruit)
    # enumerate gives index + value together

# Looping with zip()

names = ["A", "B", "C"]
scores = [90, 85, 88]

for name, score in zip(names, scores):
    print(name, score)
    # zip combines multiple lists element-wise


# List Comprehension (Short loop)
squares = [i*i for i in range(5)]
print(squares)
# Compact form of for loop
# Creates a new list

# pass in loops
for i in range(3):
    pass
    # pass does nothing
    # Used as placeholder

Note: Python supports for and while loops, with control statements like break, continue, and else to manage loop execution.
```
## 📌40. Python Lists (Array Equivalent)
```python
A list is:

=> Ordered
=> Mutable (can change)
=> Can store mixed data types
=> Most used data structure in Python

# Creating a list
numbers = [1, 2, 3, 4]
# A list of integers

mixed = [1, "Python", True, 3.5]
# List can store different data types

# Accessing elements (Indexing)
fruits = ["apple", "banana", "mango"]

print(fruits[0])    # apple
# Index starts from 0

print(fruits[-1])   # mango
# Negative index starts from end


# Slicing (Get part of list)

nums = [10, 20, 30, 40, 50]

print(nums[1:4])   # [20, 30, 40]
# Starts from index 1
# Ends before index 4

# Modifying list values (Mutable nature)

nums = [1, 2, 3]

nums[1] = 20
print(nums)
# Lists are mutable → values can be changed

# Adding elements (IMPORTANT METHODS)
 => # append() → Add at end

nums = [1, 2, 3]

nums.append(4)
# Adds element at the end

=> # insert() → Add at specific position
nums.insert(1, 99)
# Inserts 99 at index 1

=> # extend() → Add multiple elements
nums.extend([5, 6])
# Adds elements from another list

# Removing elements
=> # remove() → Remove by value
nums = [1, 2, 3, 2]

nums.remove(2)
# Removes first occurrence of 2

=> # pop() → Remove by index
nums.pop(1)
# Removes element at index 1

=> # clear() → Remove all items
nums.clear()
# List becomes empty


# Finding elements
=> # index() → Get index of value
nums = [10, 20, 30]

print(nums.index(20))
# Returns index of 20

=> # count() → Count occurrences
nums = [1, 2, 2, 3]

print(nums.count(2))
# Counts how many times 2 appears

# Sorting and reversing
=> # sort() → Sort list
nums = [3, 1, 4, 2]

nums.sort()
# Sorts list in ascending order

=> # reverse() → Reverse list
nums.reverse()
# Reverses element order

# Copying lists

a = [1, 2, 3]      # Create a list 'a'
 
b = a              # 'b' points to the SAME list as 'a' (reference copy)
# Now both 'a' and 'b' refer to the same object in memory

c = a.copy()       # 'c' is a NEW list with the same elements (actual copy - shallow copy)
# 'c' refers to a different list object

b.append(4)        # Append 4 to the list THROUGH 'b'
# Since 'b' and 'a' are the same list, this change affects 'a' too

print(a)  # [1, 2, 3, 4]  -> 'a' shows the change
print(c)  # [1, 2, 3]     -> 'c' is unchanged because it's a separate copy

# Membership check
fruits = ["apple", "banana"]

print("apple" in fruits)
# Checks if element exists in list

# Length of list
nums = [1, 2, 3]

print(len(nums))
# Number of elements in list

# Nested lists (2D list)
matrix = [
    [1, 2],
    [3, 4]
]

print(matrix[1][0])  # 3
```
## 📌41. Tuple (Immutable List)
```python
A tuple is:

=> Ordered
=> Immutable (cannot be changed after creation)
=> Faster than lists
=> Safer for fixed data

# Creating a tuple
t1 = (1, 2, 3)
# Tuple with multiple values

t2 = 1, 2, 3
# Parentheses are optional

t3 = (5,)
# Single-element tuple (comma is REQUIRED)

Note: Use tuple when data should not change.

# Accessing elements (Indexing)
colors = ("red", "green", "blue")

print(colors[0])    # red
# Index starts from 0

print(colors[-1])   # blue
# Negative index starts from end

# Slicing tuple
nums = (10, 20, 30, 40, 50)

print(nums[1:4])   # (20, 30, 40)
# Returns a new tuple


# Immutability (IMPORTANT)
nums = (1, 2, 3)

# nums[0] = 10   Error
# Tuples cannot be modified
Note: This is why tuples are safe and hashable.

# Tuple methods (ONLY 2 METHODS)
# count() → Count occurrences

nums = (1, 2, 2, 3)

print(nums.count(2))  
# Counts how many times 2 appears

# index() → Find index of value
nums = (10, 20, 30)

print(nums.index(20))  
# Returns index of 20

# Built-in functions used with tuples
# len() → Number of elements

t = (1, 2, 3)

print(len(t))
# Total elements in tuple

# max() → Largest value
max() → Largest value

# min() → Smallest value
print(min(nums))
# Returns lowest value

# sum() → Sum of elements
print(sum(nums))
# Adds all values together


# sorted() → Sort tuple (returns list)
nums = (3, 1, 2)

print(sorted(nums))
# Returns a LIST, not tuple


# Looping through tuple
fruits = ("apple", "banana", "mango")

for fruit in fruits:
    print(fruit)
    # Reads values one by one

# Tuple unpacking (VERY IMPORTANT)
person = ("Monu", 25)

name, age = person
# Values unpacked into variables

print(name)
print(age)

# Swapping variables (Python trick)
a = 10
b = 20

a, b = b, a

# Uses tuple packing & unpacking
a = 10
b = 20

a, b = b, a
# Uses tuple packing & unpacking

# Nested tuples
data = ((1, 2), (3, 4))

print(data[1][0])  # 3

# Membership check
colors = ("red", "green")

print("red" in colors)
# Checks if value exists

```
## 📌42. Python Set (Unique Values)
```python
A set is:

=> Unordered
=> Stores unique values only
=> Mutable (but elements must be immutable)
=> Very fast for lookup

# Creating a set
nums = {1, 2, 3}
# Set with unique values

nums2 = {1, 2, 2, 3}
print(nums2)
# Duplicate values are automatically removed

empty_set = set()
# Correct way to create empty set


# Important property (Unordered)
colors = {"red", "green", "blue"}
print(colors)
# Order is NOT guaranteed

Note: Never rely on position or indexing in sets.

# Adding elements
=> # add() → Add single element

nums = {1, 2}

nums.add(3)
# Adds 3 to set


=> # update() → Add multiple elemen
nums.update([4, 5])
# Adds multiple elements

# Removing elements
=> # remove() → Remove element (Error if not found)
nums.remove(2)
# Removes 2


=> # discard() → Safe remove (No error)
nums.discard(10)
# Does nothing if element not found

=> # pop() → Remove random element
nums.pop()
# Removes an arbitrary element

# clear() → Remove all elements
nums.clear()
# Set becomes empty


# Membership check (FAST)
nums = {1, 2, 3}

print(2 in nums)
# Very fast lookup

Note: Use sets for existence checking.

# Set operations (VERY IMPORTANT)
=> # Union → Combine sets

a = {1, 2}
b = {2, 3}

print(a | b)
# All unique elements from both sets

=> # Intersection → Common elements
print(a & b)
# Elements present in both sets

=> # Difference → Only in first set
print(a - b)
# Elements in a but not in b

=> # Symmetric Difference → In either but not both
print(a ^ b)
# Elements that are not common


# Built-in set methods

=> # len() → Size of set
print(len(a))
# Number of elements

=> # copy() → Shallow copy
c = a.copy()
# Creates a new set

=> # isdisjoint() → No common elements
x = {1, 2}
y = {3, 4}

print(x.isdisjoint(y))
# True if no common values

=> # issubset() → Check subset
small = {1, 2}
big = {1, 2, 3}

print(small.issubset(big))

=> # issuperset() → Check superset
print(big.issuperset(small))


# Looping through set
fruits = {"apple", "banana"}

for fruit in fruits:
    print(fruit)
    # Order may change each run

# Frozen set (Immutable set)
fs = frozenset([1, 2, 3])
# Immutable version of set

Note: Use when set should not change.
```
## 📌43. Dictionary (Object Equivalent)
```python
# Creating a dictionary
student = {
    "name": "Monu",
    "age": 22,
    "course": "Python"
}
# Keys are strings, values can be anything
Note: Use dictionary when data has meaningful keys

# Accessing values
print(student["name"])
# Access value using key
Note: Error if key not found

# Using get() (SAFE way)
print(student.get("age"))
print(student.get("salary"))
print(student.get("salary", 0))
Note: Use get() to avoid errors

# Adding / Updating values
student["age"] = 23
student["city"] = "Delhi"
# Updates existing key
# Adds new key if not present


# Removing items
=> # pop() → remove by key
student.pop("city")
# Removes key and returns its value

=> # popitem() → remove last inserted item
student.popitem()
# Removes last key-value pair

=> # del
del student["age"]
# Deletes specific key

=> # clear()
student.clear()
# Removes all items


# Dictionary views (VERY IMPORTANT)

data = {"a": 1, "b": 2, "c": 3}

=> # keys()
print(data.keys())

=> # values()
print(data.values())

=> # items()
print(data.items())

# Looping through dictionary
=> # Loop keys
for key in data:
    print(key)

=> # Loop values
for value in data.values():
    print(value)

=> # Loop key & value (MOST USED)
for key, value in data.items():
    print(key, "=>", value)

# Checking existence
print("a" in data)
print("z" not in data)

# update() → merge dictionaries
a = {"x": 1}
b = {"y": 2, "x": 5}

a.update(b)
print(a)

Note: Existing keys get overwritten

# setdefault() (INTERVIEW FAVORITE)
user = {"name": "Monu"}

user.setdefault("age", 25)
user.setdefault("name", "Amit")

print(user)
Note: Adds key only if it doesn’t exist

# Copying dictionary (IMPORTANT)
a = {"x": 1}
b = a          # Reference copy
c = a.copy()   # Actual copy

b["x"] = 10

print(a)
print(c)

# Nested dictionary
users = {
    "user1": {"name": "Monu", "age": 22},
    "user2": {"name": "Amit", "age": 25}
}

print(users["user1"]["name"])

# Dictionary comprehension
squares = {x: x*x for x in range(5)}
print(squares)

# Built-in functions with dictionary
=> # len()
print(len(data))

=> # str()
print(str(data))

=> # type()
print(type(data))

# Keys rules (IMPORTANT)
d = {
    1: "int",
    "a": "string",
    (1, 2): "tuple"
}
# Keys must be IMMUTABLE

❌ Not allowed:
# {[1,2]: "list"}  ❌

```
## 📌44. Functions (Reusable Logic)
```python
# Basic function (no input, no output)
def greet():
    print("Hello, welcome!")
    # Function body runs when function is called

greet()


# Function with parameters (input)
def greet(name):
    print("Hello", name)
    # 'name' is a parameter

greet("Monu")


# Function with return value
def add(a, b):
    return a + b
    # return sends result back to caller

result = add(10, 5)
print(result)
Note: Use return when you need output.

# Function with multiple returns
def calculate(a, b):
    return a + b, a - b
    # Returns a tuple

sum_val, diff_val = calculate(10, 5)
print(sum_val, diff_val)


# Default parameter values
def greet(name="Guest"):
    print("Hello", name)
    # Default value used if argument not passed

greet()
greet("Monu")


# Keyword arguments
def profile(name, age):
    print(name, age)

profile(age=22, name="Monu")
# Order does not matter

# Positional vs Keyword arguments
def info(name, city):
    print(name, city)

info("Monu", "Delhi")       # Positional
info(city="Delhi", name="Monu")  # Keyword


# Variable-length arguments
=> # *args → multiple positional arguments

def total(*numbers):
    return sum(numbers)
    # numbers is a tuple

print(total(1, 2, 3, 4))


=> # **kwargs → multiple keyword arguments
def details(**info):
    print(info)
    # info is a dictionary

details(name="Monu", age=22)


# Function inside function (Nested)
def outer():
    def inner():
        print("Inner function")
    inner()

outer()

# Scope of variables (LEGB Rule)
x = 10   # Global

def test():
    x = 5  # Local
    print(x)

test()
print(x)


# global keyword


count = 0  # This is a global (module-level) variable

def increase():
    # Tell Python we want to use the global 'count', not create a local one
    global count
    count += 1  # Modify the global variable

increase()        # Call the function, it increases 'count' by 1
print(count)      # Output: 1


# nonlocal keyword
def outer():
    x = 10              # 'x' lives in the outer() function's scope

    def inner():
        nonlocal x      # Tell Python: use the 'x' from outer(), not a new local one
        x += 5          # Modify that 'x' by adding 5

    inner()             # Call inner(), which increases x from 10 to 15
    print(x)            # Prints the updated value of x -> 15

outer()                  # Output: 15

# Lambda function (Anonymous)
add = lambda a, b: a + b
print(add(3, 4))


# Docstrings (Documentation)
def add(a, b):
    """Returns sum of two numbers"""
    return a + b

print(add.__doc__)


# Recursion (Function calling itself)
def factorial(n):
    if n == 1:
        return 1
    return n * factorial(n - 1)

print(factorial(5))

# Higher-order functions
def square(x):
    return x * x

nums = [1, 2, 3]

result = list(map(square, nums))
print(result)

# Function as argument
def apply(func, value):
    return func(value)

print(apply(abs, -10))


# Return vs Print (INTERVIEW
def show():
    print(10)

def give():
    return 10

print(show())   # None
print(give())   # 10
```
## 📌45. Python File Handling (Read / Write Files)
```python
# Opening a file
file = open("data.txt", "r")
# "data.txt" → file name
# "r" → read mode


| Mode | Meaning                 |
| ---- | ----------------------- |
| `r`  | Read (file must exist)  |
| `w`  | Write (overwrites file) |
| `a`  | Append (adds at end)    |
| `x`  | Create new file         |
| `rb` | Read binary             |
| `wb` | Write binary            |

# Reading file content
=> # read() → Read full file

file = open("data.txt", "r")

content = file.read()
print(content)
# Reads entire file as a single string

file.close()


=> # readline() → Read one line
file = open("data.txt", "r")

line = file.readline()
print(line)
# Reads only first line

file.close()

=> # readlines() → Read all lines as list
file = open("data.txt", "r")

lines = file.readlines()
print(lines)
# Each line becomes an element in list

file.close()


# Loop through file (BEST PRACTICE)
file = open("data.txt", "r")

for line in file:
    print(line.strip())
    # Reads file line by line
    # strip() removes newline

file.close()

# Writing to file
=> # write() → Write text
file = open("data.txt", "w")

file.write("Hello Python\n")
file.write("File handling example")
# Overwrites existing file

file.close()


# Appending to file
file = open("data.txt", "a")

file.write("\nNew line added")
# Adds data at the end

file.close()

# Using with (RECOMMENDED)
with open("data.txt", "r") as file:
    content = file.read()
    print(content)
    # File closes automatically

Note: Avoids forgetting close()

# Check file exists
import os

print(os.path.exists("data.txt"))
# True if file exists

# File pointer (seek and tell)
file = open("data.txt", "r")

print(file.tell())
# Current cursor position

file.seek(0)
# Move cursor to beginning

file.close()

# Binary file handling
with open("image.jpg", "rb") as file:
    data = file.read()
    # Reads binary data

# Writing list data to file
lines = ["Python\n", "Java\n", "C++\n"]

with open("languages.txt", "w") as file:
    file.writelines(lines)

# Reading file safely (Exception handling)
try:
    with open("data.txt", "r") as file:
        print(file.read())
except FileNotFoundError:
    print("File not found")


# Rename and delete file
import os

os.rename("old.txt", "new.txt")
# Renames file

os.remove("new.txt")
# Deletes file

```
## 📌45. OOPS Concepts
```python
# Core OOPS Concepts
=> Class
=> Object
=> Constructor (__init__)
=> Instance variables
=> Methods
=> Encapsulation
=> Inheritance
=> Polymorphism
=> Abstraction

We’ll cover everything step by step 

# Class (Blueprint)
A class is a blueprint/template for creating objects.

class Person:
    pass
# Empty class
Note: Class defines what an object will have and do

# Object (Real Instance)
An object is created from a class.

p1 = Person()
# p1 is an object of Person class
Note: One class → many objects

# Constructor (__init__)
Constructor runs automatically when object is created.

class Person:
    def __init__(self, name, age):
        self.name = name
        # self.name is instance variable

        self.age = age

p1 = Person("Monu", 22)

Note: 
What is self?
=> self refers to the current object
=> Used to access variables & methods inside class

# Instance Variables
Variables that belong to each object.

class Person:
    def __init__(self, name):
        self.name = name

p1 = Person("John")
p2 = Person("Alice")

print(p1.name)  # John
print(p2.name)  # Alice

Note: Each object has its own copy

# Methods (Functions inside class)
class Person:
    def greet(self):
        print("Hello, my name is", self.name)

p = Person("Monu")
p.greet()
Note: Methods define behavior

Complete Simple Example (Very Important)

class Student:
    def __init__(self, name, marks):
        self.name = name
        self.marks = marks

    def is_pass(self):
        return self.marks >= 40
        # Business logic inside class

s1 = Student("Monu", 75)

print(s1.is_pass())   # True


# Class Variables (Shared by all objects)

class Student:
    school = "ABC School"   # Class variable

    def __init__(self, name):
        self.name = name    # Instance variable

s1 = Student("Monu")
s2 = Student("Amit")

print(s1.school)
print(s2.school)
Note: Class variable is shared

# Encapsulation (Data Protection)
Encapsulation = hide internal data

Private variable (by convention)
class Account:
    def __init__(self, balance):
        self.__balance = balance
        # __ makes it private

    def get_balance(self):
        return self.__balance

acc = Account(5000)
print(acc.get_balance())

Note: Prevents direct access

# Getter & Setter

class Account:
    def __init__(self, balance):
        self.__balance = balance

    def set_balance(self, amount):
        if amount >= 0:
            self.__balance = amount

    def get_balance(self):
        return self.__balance

# Inheritance (Reuse Code)
Inheritance = one class inherits another class.

class Animal:
    def sound(self):
        print("Animal sound")

class Dog(Animal):
    def bark(self):
        print("Dog barks")

d = Dog()
d.sound()
d.bark()
Note: Dog gets features of Animal

# Method Overriding
class Animal:
    def sound(self):
        print("Animal sound")

class Dog(Animal):
    def sound(self):
        print("Dog barks")

d = Dog()
d.sound()
Note: Child class overrides parent method


# Polymorphism (Many Forms)
Same method name, different behavior.

class Cat:
    def sound(self):
        print("Meow")

class Dog:
    def sound(self):
        print("Bark")

animals = [Cat(), Dog()]

for a in animals:
    a.sound()
Note: Works because method name is same


# super() keyword

Used to call parent class methods.
class Animal:
    def __init__(self):
        print("Animal constructor")

class Dog(Animal):
    def __init__(self):
        super().__init__()
        print("Dog constructor")

Dog()


# Abstraction (Hiding Implementation)
Using abc module.

from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self):
        pass

class Square(Shape):
    def area(self):
        return 4 * 4

s = Square()
print(s.area())
Note: Forces child class to implement methods

# __str__ (Readable Object Output)

class Person:
    def __init__(self, name):
        self.name = name

    def __str__(self):
        return f"Person name is {self.name}"

p = Person("Monu")
print(p)

# isinstance() (Type check)
print(isinstance(p, Person))  # True


# Object Comparison
class Point:
    def __init__(self, x):
        self.x = x

p1 = Point(5)
p2 = Point(5)

print(p1 == p2)   # False (different objects)
```
#  Practice python mode

## 📌1. Reverse String without method
```python

str = "hello"
result = ""

for char in str:
    result = char + result

print(result)
```
## 📌2. Check String Palindrome
```python
str = "madam"

def is_palindrom(str):
    left = 0
    right = len(str) -1
    
    while left < right:
        if str[left] != str[right]:
            return False
            break
        left +=1
        right -=1
    
    return True

print(is_palindrom(str))
```
## 📌3. Find Square of a Number
```python
import math

num= 4

def square(num):
    # solution 1 
    return math.pow(num, 2)
    
    # solution 2
    return num * num
print(square(num))
```
## 📌4. Count Characters in String
```python
str = "hello"

def find_length(str):
    # return len(str)
    count = 0
    
    for char in str:
        count += 1
        
    return count
    
print(find_length(str))
```
## 📌5. Find Maximum of Two Numbers
```python
a, b = 10, 20

def find_max_num(a, b):
    # return max(a, b)
    
    # return a if a > b else b
    
    if(a > b):
        return a
    else:
        return b
    
print(find_max_num(a, b))
```
## 📌6. Sum of Digits
```python

digits = 1234
# output 10

def sum_of_digits(digits):
    sum = 0
    
    for num in str(digits):
        sum += int(num)
    return sum

print(sum_of_digits(digits))
```
## 📌7. Multiplication Table
```python
def print_table(num):
    # solution 1
    for i in range(1, 11):
        print(f"{num} * {i} = {num * i}")
        
    # solution 2
    
    i = 1
    
    while i <= 10:
        print(f"{num} * {i} = {num * i}")
        i+=1
    
print(print_table(5)) 
```
## 📌8. Count Vowels
```python
str = "education"
# output = 5

def count_vowel(str):
    vowel = "aeiouAEIOU"
    count = 0
    
    for v in vowel:
        count += str.count(v)
    
    return count
print(count_vowel(str))    
```
## 📌9. Factorial of a Number
```python
num = 5

def factorial(num):
    # solution 1
    if num == 0 or num == 1:
        return 1
    return num * factorial(num - 1)
    
    
    # solution 2
    fact = 1
    while num > 0:
        fact *= num
        num -= 1
    return fact

    # solution 3
    import math
    print(math.factorial(5))
print(factorial(num))
```
## 📌10. Check Prime Number
```python

num = 13
def is_prime(num):
    if num <= 1:
        return "Not Prime!"
        
    for i in range(2, num):
        if num % i == 0:
            return "Not Prime!"
    
    return "Prime Number"
    
print(is_prime(num))
```
## 📌11. Fibonacci Series
```python
n = 5

def fibonacci(num):
    if num <= 1:
        return num
    return fibonacci(num - 1) + fibonacci(num - 2)

def fibonacci_series(n):
    for i in range(n):
        print(fibonacci(i), end=" ")

fibonacci_series(n)
```
## 📌12. Remove Duplicates from List
```python
nums = [1, 2, 2, 3, 4, 4, 5]

def remove_duplicate(nums):
    # solution 1
    return list(set(nums))
    
    # solution 2
    result = []
    
    for n in nums:
        if n not in result:
            result.append(n)
    return result
    
    # solution 3
    return list(dict.fromkeys(nums))
    
print(remove_duplicate(nums))
```
## 📌13. Find Second Largest Number
```python

nums = [10, 20, 30, 40]

def find_second_largest(nums):
    # solution 1
    
    largest = float('-inf')
    second_largest = float('-inf')
    
    for num in nums:
        if num > largest:
            second_largest = largest
            largest=num
        elif num > second_largest and num != largest:
            second_largest = num
        
    
    return largest, second_largest

print(find_second_largest(nums))
```
## 📌14. Count Words in Sentence
```python
str = "I love Python programming"

def count_word(str):
    # solution 1
    return len(str.split())
    
    # solution 2
    count = 0
    for word in str.split():
        count += 1
    return count
    
print(count_word(str))   
```
## 📌15. Check Anagram
```python
from collections import Counter
s1 = "listen"
s2 = "silent"

def check_anagram(s1, s2):
    # solution
    same = sorted(s1) == sorted(s2)
    if same:
        return "Anagram"
    else:
        return "Not Anagram"
    
    # solution 2
    if len(s1) != len(s2):
        return "Not Anagram"
    else:
        count = {}
        for ch in s1:
            count[ch] = count.get(ch, 0)+1
        
        for ch in s2:
            if ch not in count or count[ch] == 0:
                return "Not Anagram"
            count[ch] -= 1
            
    return "Anagram"

    # solution 3
    if Counter(s1) != Counter(s2):
          return "Not Anagram!"
    else:
         return "Anagram"
          
print(check_anagram(s1, s2))
```
## 📌16. Find Common Elements in Two Lists
```python
list1 = [1, 2, 3, 4]
list2 = [3, 4, 5, 6]

# output [3, 4]
def common_element(list1, list2):
    common = []
    
    for num in list1:
        if num in list2 and num not in common:
            common.append(num)
    
    return common

print(common_element(list1, list2))
```

