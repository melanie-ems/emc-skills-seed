# Python Quick Reference Guide

A handy reference for common Python syntax and concepts covered in this course.

## Table of Contents
1. [Basic Syntax](#basic-syntax)
2. [Variables and Data Types](#variables-and-data-types)
3. [Operators](#operators)
4. [Control Flow](#control-flow)
5. [Loops](#loops)
6. [Functions](#functions)
7. [Data Structures](#data-structures)
8. [Common Built-in Functions](#common-built-in-functions)
9. [String Methods](#string-methods)
10. [List Methods](#list-methods)

---

## Basic Syntax

### Comments
```python
# Single line comment

"""
Multi-line comment
or docstring
"""
```

### Print
```python
print("Hello")              # Simple print
print("Hello", "World")     # Multiple items
print(f"Value: {x}")        # F-string
```

### Input
```python
name = input("Enter name: ")     # Returns string
age = int(input("Enter age: "))  # Convert to int
```

---

## Variables and Data Types

### Variable Assignment
```python
x = 10              # Integer
name = "Alice"      # String
price = 9.99        # Float
is_valid = True     # Boolean
```

### Type Checking and Conversion
```python
type(x)             # Check type
int("42")           # String to integer
float("3.14")       # String to float
str(42)             # Integer to string
bool(1)             # Integer to boolean
```

---

## Operators

### Arithmetic
```python
+       # Addition
-       # Subtraction
*       # Multiplication
/       # Division (float)
//      # Floor division (integer)
%       # Modulo (remainder)
**      # Exponent
```

### Comparison
```python
==      # Equal to
!=      # Not equal to
>       # Greater than
<       # Less than
>=      # Greater than or equal
<=      # Less than or equal
```

### Logical
```python
and     # Both conditions must be True
or      # At least one condition must be True
not     # Reverse the condition
```

---

## Control Flow

### If Statements
```python
if condition:
    # code if True
elif other_condition:
    # code if other_condition is True
else:
    # code if all conditions are False
```

### Examples
```python
# Simple if
if age >= 18:
    print("Adult")

# If-else
if score >= 60:
    print("Pass")
else:
    print("Fail")

# If-elif-else
if score >= 90:
    grade = "A"
elif score >= 80:
    grade = "B"
elif score >= 70:
    grade = "C"
else:
    grade = "F"

# Combining conditions
if age >= 18 and has_license:
    print("Can drive")

if is_weekend or is_holiday:
    print("Day off!")
```

---

## Loops

### For Loop
```python
# Basic for loop
for i in range(5):
    print(i)  # 0, 1, 2, 3, 4

# Range with start and stop
for i in range(2, 5):
    print(i)  # 2, 3, 4

# Range with step
for i in range(0, 10, 2):
    print(i)  # 0, 2, 4, 6, 8

# Loop through string
for char in "Python":
    print(char)

# Loop through list
for item in [1, 2, 3]:
    print(item)
```

### While Loop
```python
# Basic while loop
count = 0
while count < 5:
    print(count)
    count += 1

# While with condition
while True:
    answer = input("Continue? (y/n): ")
    if answer == 'n':
        break
```

### Loop Control
```python
break       # Exit loop immediately
continue    # Skip to next iteration

# Example with break
for i in range(10):
    if i == 5:
        break  # Stop at 5

# Example with continue
for i in range(10):
    if i % 2 == 0:
        continue  # Skip even numbers
    print(i)
```

---

## Functions

### Basic Function
```python
def greet():
    print("Hello!")

greet()  # Call function
```

### Function with Parameters
```python
def greet(name):
    print(f"Hello, {name}!")

greet("Alice")
```

### Function with Return
```python
def add(a, b):
    return a + b

result = add(5, 3)  # result = 8
```

### Default Parameters
```python
def greet(name="Friend"):
    print(f"Hello, {name}!")

greet()         # "Hello, Friend!"
greet("Alice")  # "Hello, Alice!"
```

### Multiple Return Values
```python
def get_stats(numbers):
    return min(numbers), max(numbers)

minimum, maximum = get_stats([1, 5, 3])
```

### Docstring
```python
def calculate_area(width, height):
    """Calculate rectangle area.
    
    Args:
        width: Rectangle width
        height: Rectangle height
    
    Returns:
        Area of rectangle
    """
    return width * height
```

---

## Data Structures

### Lists (Mutable)
```python
# Create list
fruits = ["apple", "banana", "orange"]
numbers = [1, 2, 3, 4, 5]
mixed = [1, "hello", 3.14, True]

# Access elements
fruits[0]       # "apple" (first)
fruits[-1]      # "orange" (last)
fruits[1:3]     # ["banana", "orange"] (slice)

# Modify list
fruits[0] = "grape"         # Change element
fruits.append("mango")      # Add to end
fruits.insert(1, "kiwi")    # Insert at position
fruits.remove("banana")     # Remove by value
fruits.pop()                # Remove and return last
fruits.pop(0)               # Remove and return at index

# List operations
len(fruits)                 # Length
"apple" in fruits           # Check membership
fruits + ["pear"]           # Concatenate
fruits * 2                  # Repeat
```

### Tuples (Immutable)
```python
# Create tuple
point = (10, 20)
rgb = (255, 128, 0)

# Access elements
point[0]        # 10
x, y = point    # Unpack tuple
```

### Dictionaries (Key-Value Pairs)
```python
# Create dictionary
person = {
    "name": "Alice",
    "age": 25,
    "city": "New York"
}

# Access values
person["name"]              # "Alice"
person.get("age")           # 25
person.get("email", "N/A")  # "N/A" (default)

# Modify dictionary
person["age"] = 26          # Update value
person["email"] = "a@b.com" # Add new key
del person["city"]          # Delete key

# Dictionary operations
"name" in person            # Check if key exists
person.keys()               # Get all keys
person.values()             # Get all values
person.items()              # Get all key-value pairs

# Loop through dictionary
for key in person:
    print(key, person[key])

for key, value in person.items():
    print(f"{key}: {value}")
```

---

## Common Built-in Functions

```python
# Type conversion
int("42")           # String to integer
float("3.14")       # String to float
str(42)             # Integer to string

# Math functions
abs(-10)            # Absolute value: 10
round(3.14159, 2)   # Round to 2 decimals: 3.14
min(1, 2, 3)        # Minimum: 1
max(1, 2, 3)        # Maximum: 3
sum([1, 2, 3])      # Sum: 6

# String/List functions
len("hello")        # Length: 5
len([1, 2, 3])      # Length: 3

# Type checking
type(42)            # <class 'int'>
isinstance(42, int) # True

# Range
range(5)            # 0, 1, 2, 3, 4
range(2, 5)         # 2, 3, 4
range(0, 10, 2)     # 0, 2, 4, 6, 8

# Input/Output
input("Prompt: ")   # Get user input
print("text")       # Print to console
```

---

## String Methods

```python
text = "Hello World"

# Case conversion
text.upper()        # "HELLO WORLD"
text.lower()        # "hello world"
text.title()        # "Hello World"
text.capitalize()   # "Hello world"

# Checking content
text.isdigit()      # False
text.isalpha()      # False (has space)
text.startswith("H") # True
text.endswith("d")  # True

# Searching and replacing
text.find("World")  # 6 (index of "W")
text.replace("World", "Python")  # "Hello Python"
text.count("l")     # 3

# Splitting and joining
text.split()        # ["Hello", "World"]
"-".join(["a", "b", "c"])  # "a-b-c"

# Stripping whitespace
"  hello  ".strip() # "hello"
"  hello  ".lstrip() # "hello  "
"  hello  ".rstrip() # "  hello"
```

---

## List Methods

```python
numbers = [3, 1, 4, 1, 5]

# Adding elements
numbers.append(6)       # Add to end: [3, 1, 4, 1, 5, 6]
numbers.insert(0, 0)    # Insert at index: [0, 3, 1, 4, 1, 5, 6]
numbers.extend([7, 8])  # Add multiple: [3, 1, 4, 1, 5, 7, 8]

# Removing elements
numbers.remove(1)       # Remove first 1: [3, 4, 1, 5]
numbers.pop()           # Remove and return last
numbers.pop(0)          # Remove and return at index
numbers.clear()         # Remove all elements

# Organizing
numbers.sort()          # Sort in place: [1, 1, 3, 4, 5]
numbers.reverse()       # Reverse in place: [5, 4, 3, 1, 1]
sorted(numbers)         # Return sorted copy
numbers.index(4)        # Find index of value: 2
numbers.count(1)        # Count occurrences: 2

# Copying
numbers.copy()          # Shallow copy
numbers[:]              # Slice copy
```

---

## F-Strings (String Formatting)

```python
name = "Alice"
age = 25
price = 19.99

# Basic f-string
f"Hello, {name}!"                    # "Hello, Alice!"

# Expressions
f"Next year: {age + 1}"              # "Next year: 26"

# Formatting numbers
f"Price: ${price:.2f}"               # "Price: $19.99"
f"Percentage: {0.875:.1%}"           # "Percentage: 87.5%"

# Alignment
f"{name:>10}"                        # "     Alice" (right align)
f"{name:<10}"                        # "Alice     " (left align)
f"{name:^10}"                        # "  Alice   " (center)

# Padding
f"{age:05}"                          # "00025" (pad with zeros)
```

---

## Common Patterns

### Read user input until valid
```python
while True:
    try:
        age = int(input("Enter age: "))
        if age > 0:
            break
        print("Age must be positive")
    except ValueError:
        print("Please enter a number")
```

### Sum a list of numbers
```python
total = sum(numbers)

# Or with loop
total = 0
for num in numbers:
    total += num
```

### Count occurrences
```python
count = 0
for item in items:
    if item == target:
        count += 1
```

### Build a list
```python
# Traditional
squares = []
for i in range(5):
    squares.append(i ** 2)

# List comprehension
squares = [i ** 2 for i in range(5)]
```

### Menu loop
```python
while True:
    print("1. Option 1")
    print("2. Option 2")
    print("3. Exit")
    
    choice = input("Choose: ")
    
    if choice == "1":
        # Do something
        pass
    elif choice == "2":
        # Do something else
        pass
    elif choice == "3":
        print("Goodbye!")
        break
    else:
        print("Invalid choice")
```

---

## Tips and Tricks

### Multiple assignment
```python
x, y, z = 1, 2, 3
a = b = c = 0
```

### Swapping values
```python
a, b = b, a
```

### Checking multiple conditions
```python
if x in [1, 2, 3]:      # Check if x is 1, 2, or 3
if 0 <= x <= 10:        # Check if x is between 0 and 10
```

### Default values
```python
value = user_input or "default"
```

### Ternary operator
```python
result = "Pass" if score >= 60 else "Fail"
```

---

**Keep this guide handy while coding!** 

For more details on any topic, refer back to the relevant lesson or check the [Additional Resources](ADDITIONAL_RESOURCES.md).
