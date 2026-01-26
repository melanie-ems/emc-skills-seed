# Lesson 5: Functions - Writing Reusable Code

## Introduction

Imagine you need to calculate the area of rectangles many times in your program. Instead of writing the same code repeatedly, you can create a **function** - a reusable block of code with a name.

Functions help you:
- Avoid repeating code (DRY - Don't Repeat Yourself)
- Organize code into logical pieces
- Make code easier to test and debug
- Share code between programs

## What is a Function?

A function is a named block of code that performs a specific task:

```python
def greet():
    print("Hello, World!")

# Call the function
greet()  # Output: Hello, World!
```

**Parts of a function:**
1. `def` - keyword that starts a function definition
2. `greet` - the function name
3. `()` - parentheses (may contain parameters)
4. `:` - colon to start the function body
5. Indented code - what the function does

## Functions with Parameters

Parameters let you pass information to functions:

```python
def greet(name):
    print(f"Hello, {name}!")

# Call with different arguments
greet("Alice")   # Hello, Alice!
greet("Bob")     # Hello, Bob!
```

**Terminology:**
- **Parameter:** Variable in the function definition (`name`)
- **Argument:** Value passed when calling (`"Alice"`, `"Bob"`)

### Multiple Parameters

```python
def introduce(name, age, city):
    print(f"My name is {name}")
    print(f"I am {age} years old")
    print(f"I live in {city}")

introduce("Alice", 25, "New York")
```

### Default Parameters

Give parameters default values:

```python
def greet(name="Friend"):
    print(f"Hello, {name}!")

greet("Alice")  # Hello, Alice!
greet()         # Hello, Friend!
```

```python
def power(base, exponent=2):
    return base ** exponent

print(power(5))      # 25 (5^2)
print(power(5, 3))   # 125 (5^3)
```

## Return Values

Functions can return results using `return`:

```python
def add(a, b):
    result = a + b
    return result

sum_value = add(5, 3)
print(sum_value)  # 8
```

### Multiple Return Values

```python
def get_min_max(numbers):
    minimum = min(numbers)
    maximum = max(numbers)
    return minimum, maximum

min_val, max_val = get_min_max([1, 5, 3, 9, 2])
print(f"Min: {min_val}, Max: {max_val}")  # Min: 1, Max: 9
```

### Return vs. Print

```python
# ❌ This prints but returns None
def add_print(a, b):
    print(a + b)

result = add_print(5, 3)  # Prints: 8
print(result)             # Prints: None

# ✅ This returns a value
def add_return(a, b):
    return a + b

result = add_return(5, 3)
print(result)  # Prints: 8
```

**Key difference:** `return` lets you use the result later; `print` just shows it once.

## Function Scope

Variables created inside functions are **local** - they only exist inside the function:

```python
def my_function():
    local_var = "I'm local"
    print(local_var)

my_function()  # Works fine
print(local_var)  # Error! local_var doesn't exist here
```

**Global vs. Local:**

```python
global_var = "I'm global"

def my_function():
    local_var = "I'm local"
    print(global_var)   # Can read global
    print(local_var)    # Can read local

my_function()
print(global_var)  # Works
print(local_var)   # Error!
```

## Docstrings

Document your functions with docstrings:

```python
def calculate_area(width, height):
    """
    Calculate the area of a rectangle.
    
    Parameters:
        width (float): The width of the rectangle
        height (float): The height of the rectangle
    
    Returns:
        float: The area of the rectangle
    """
    return width * height
```

Access docstrings:
```python
print(calculate_area.__doc__)
help(calculate_area)
```

## Real-World Examples

### Example 1: Temperature Converter

```python
def celsius_to_fahrenheit(celsius):
    """Convert Celsius to Fahrenheit."""
    return (celsius * 9/5) + 32

def fahrenheit_to_celsius(fahrenheit):
    """Convert Fahrenheit to Celsius."""
    return (fahrenheit - 32) * 5/9

# Use the functions
temp_c = 25
temp_f = celsius_to_fahrenheit(temp_c)
print(f"{temp_c}°C = {temp_f}°F")  # 25°C = 77.0°F
```

### Example 2: Password Validator

```python
def is_valid_password(password):
    """
    Check if password meets security requirements.
    
    Requirements:
    - At least 8 characters long
    - Contains at least one digit
    - Contains at least one uppercase letter
    
    Returns:
        bool: True if valid, False otherwise
    """
    if len(password) < 8:
        return False
    
    has_digit = any(char.isdigit() for char in password)
    has_upper = any(char.isupper() for char in password)
    
    return has_digit and has_upper

# Test the function
print(is_valid_password("hello"))        # False (too short)
print(is_valid_password("Hello123"))     # True
print(is_valid_password("HELLO123"))     # True
print(is_valid_password("hello123"))     # False (no uppercase)
```

### Example 3: Grade Calculator

```python
def calculate_letter_grade(score):
    """Convert numeric score to letter grade."""
    if score >= 90:
        return "A"
    elif score >= 80:
        return "B"
    elif score >= 70:
        return "C"
    elif score >= 60:
        return "D"
    else:
        return "F"

def calculate_gpa(grades):
    """Calculate GPA from list of letter grades."""
    grade_points = {"A": 4.0, "B": 3.0, "C": 2.0, "D": 1.0, "F": 0.0}
    
    total = sum(grade_points[grade] for grade in grades)
    return total / len(grades)

# Use the functions
score = 85
letter = calculate_letter_grade(score)
print(f"Score {score} = Grade {letter}")

grades = ["A", "B", "A", "B", "C"]
gpa = calculate_gpa(grades)
print(f"GPA: {gpa:.2f}")
```

### Example 4: Simple Calculator

```python
def add(a, b):
    """Add two numbers."""
    return a + b

def subtract(a, b):
    """Subtract b from a."""
    return a - b

def multiply(a, b):
    """Multiply two numbers."""
    return a * b

def divide(a, b):
    """Divide a by b."""
    if b == 0:
        return "Error: Division by zero"
    return a / b

def calculator():
    """Run a simple calculator."""
    print("=== Simple Calculator ===")
    
    num1 = float(input("Enter first number: "))
    operator = input("Enter operator (+, -, *, /): ")
    num2 = float(input("Enter second number: "))
    
    if operator == "+":
        result = add(num1, num2)
    elif operator == "-":
        result = subtract(num1, num2)
    elif operator == "*":
        result = multiply(num1, num2)
    elif operator == "/":
        result = divide(num1, num2)
    else:
        result = "Invalid operator"
    
    print(f"Result: {result}")

# Run the calculator
calculator()
```

## Lambda Functions (Bonus!)

Short, anonymous functions:

```python
# Regular function
def square(x):
    return x ** 2

# Lambda function (one-liner)
square_lambda = lambda x: x ** 2

print(square(5))        # 25
print(square_lambda(5)) # 25
```

Useful with `map()`, `filter()`, `sorted()`:

```python
numbers = [1, 2, 3, 4, 5]

# Square all numbers
squared = list(map(lambda x: x ** 2, numbers))
print(squared)  # [1, 4, 9, 16, 25]

# Filter even numbers
evens = list(filter(lambda x: x % 2 == 0, numbers))
print(evens)  # [2, 4]

# Sort by custom key
words = ["apple", "pie", "zoo", "a"]
sorted_words = sorted(words, key=lambda x: len(x))
print(sorted_words)  # ['a', 'pie', 'zoo', 'apple']
```

## Hands-On Exercises

### Exercise 1: Basic Function

Write a function that takes a name and prints a personalized greeting.

```python
def greet_user(name):
    # Your code here
    pass

# Test it
greet_user("Alice")  # Should print a greeting
```

### Exercise 2: Area Calculator

Create functions to calculate areas of different shapes.

```python
def rectangle_area(width, height):
    # Calculate and return area
    pass

def circle_area(radius):
    # Use pi = 3.14159
    pass

def triangle_area(base, height):
    # Calculate and return area
    pass

# Test them
print(rectangle_area(5, 3))  # 15
print(circle_area(2))         # ~12.57
print(triangle_area(4, 6))    # 12.0
```

### Exercise 3: Is Prime

Write a function that checks if a number is prime.

```python
def is_prime(n):
    # Return True if prime, False otherwise
    pass

# Test it
print(is_prime(7))   # True
print(is_prime(10))  # False
print(is_prime(13))  # True
```

### Exercise 4: String Reverser

Create a function that reverses a string.

```python
def reverse_string(text):
    # Return reversed string
    pass

# Test it
print(reverse_string("hello"))  # "olleh"
print(reverse_string("Python")) # "nohtyP"
```

### Exercise 5: Factorial Calculator

Write a function to calculate factorial (n! = n × (n-1) × ... × 1).

```python
def factorial(n):
    # Calculate and return factorial
    pass

# Test it
print(factorial(5))  # 120
print(factorial(3))  # 6
print(factorial(0))  # 1
```

### Exercise 6: List Statistics

Create a function that returns multiple statistics about a list.

```python
def list_stats(numbers):
    # Return tuple: (min, max, average)
    pass

# Test it
stats = list_stats([1, 5, 3, 9, 2])
print(f"Min: {stats[0]}, Max: {stats[1]}, Avg: {stats[2]}")
```

### Exercise 7: Password Generator

Write a function that generates a random password.

```python
import random
import string

def generate_password(length=8):
    # Generate random password with letters and digits
    pass

# Test it
print(generate_password())     # 8-character password
print(generate_password(12))   # 12-character password
```

### Exercise 8: Count Vowels

Create a function that counts vowels in a string.

```python
def count_vowels(text):
    # Return number of vowels (a, e, i, o, u)
    pass

# Test it
print(count_vowels("hello"))        # 2
print(count_vowels("Python"))       # 1
print(count_vowels("aeiou"))        # 5
```

## Using AI with Functions

### Good Prompts for Copilot

```python
# Function to check if a string is a palindrome

# Function to find the nth Fibonacci number

# Function to convert a string to title case

# Function to calculate compound interest

# Function to validate email addresses
```

### Understanding Function Suggestions

When reviewing AI-suggested functions:
1. Check the function name - is it descriptive?
2. Review parameters - are they necessary and clear?
3. Examine the return value - what does it give back?
4. Read the logic - does it make sense?
5. Test with edge cases (empty strings, zero, negatives, etc.)

## Common Mistakes

### 1. Forgetting to Return

```python
# ❌ No return statement
def add(a, b):
    result = a + b  # Calculated but not returned!

# ✅ Return the result
def add(a, b):
    return a + b
```

### 2. Returning Too Early

```python
# ❌ Returns before finishing
def process_items(items):
    for item in items:
        return item  # Returns after first item!
    
# ✅ Return after loop
def process_items(items):
    processed = []
    for item in items:
        processed.append(item * 2)
    return processed
```

### 3. Not Calling the Function

```python
# ❌ Forgot parentheses
result = add  # This is the function object, not the result!

# ✅ Call with parentheses
result = add(5, 3)  # This calls the function
```

### 4. Modifying Mutable Parameters

```python
# ⚠️ Be careful with lists/dicts
def add_item(item, lst=[]):
    lst.append(item)
    return lst

# This can cause unexpected behavior!
print(add_item(1))  # [1]
print(add_item(2))  # [1, 2] - Unexpected!

# ✅ Better: Use None as default
def add_item(item, lst=None):
    if lst is None:
        lst = []
    lst.append(item)
    return lst
```

## Debugging Functions

### Test Functions Independently

```python
def my_function(x):
    # Test with print statements
    print(f"Input: {x}")
    result = x * 2
    print(f"Result: {result}")
    return result

# Test with known values
my_function(5)  # Should show: Input: 5, Result: 10
```

### Use Assert Statements

```python
def add(a, b):
    return a + b

# Test your function
assert add(2, 3) == 5, "Should be 5"
assert add(-1, 1) == 0, "Should be 0"
assert add(0, 0) == 0, "Should be 0"
print("All tests passed!")
```

## Key Concepts Summary

**Function Definition:**
- Use `def` keyword
- Give descriptive names
- Include parameters in parentheses
- Indent the function body

**Parameters:**
- Input values for functions
- Can have default values
- Can be required or optional

**Return Values:**
- Use `return` to send back results
- Functions without `return` return `None`
- Can return multiple values as tuple

**Scope:**
- Local variables exist only in function
- Global variables accessible everywhere
- Avoid modifying global variables in functions

**Best Practices:**
- Write docstrings
- Keep functions focused (do one thing well)
- Use descriptive names
- Test with various inputs

## Reflection Questions

1. Why are functions important in programming?
2. What's the difference between parameters and arguments?
3. When should you use `return` vs. `print`?
4. What is function scope and why does it matter?

## Next Steps

In Lesson 6, you'll learn about:
- Lists and tuples (ordered collections)
- Dictionaries (key-value pairs)
- Sets (unique collections)
- Working with data structures

## Additional Resources

- [Python Functions - Official Docs](https://docs.python.org/3/tutorial/controlflow.html#defining-functions)
- [Function Best Practices](https://realpython.com/defining-your-own-python-function/)
- [Python Scope](https://realpython.com/python-scope-legb-rule/)

---

**Practice Challenge:** Create a text-based game with multiple functions for different game actions!

Ready to continue? Move on to [Lesson 6: Data Structures](lesson6_data_structures.md)!
