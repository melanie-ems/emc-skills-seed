# Lesson 2: Variables and Data Types

## Introduction

In this lesson, you'll learn how to store and work with information in your programs. This is a fundamental skill that makes programs useful and interactive.

## What are Variables?

A variable is like a labeled box that stores information. Think of it as:
- A container with a name
- A way to remember values
- A reference to data that can change

### Real-World Analogy

Imagine labeled jars in a kitchen:
- A jar labeled "sugar" contains sugar
- A jar labeled "flour" contains flour
- You can use the label to get what's inside
- You can change what's inside

In Python:
```python
sugar = 2  # sugar jar has 2 cups
flour = 3  # flour jar has 3 cups
```

## Creating Variables

Creating a variable is called "assignment." You give it a name and a value:

```python
# Variable assignment
name = "Alice"
age = 25
temperature = 72.5
is_student = True
```

### Naming Rules

✅ **Good variable names:**
```python
user_name = "Bob"
total_score = 100
max_temperature = 98.6
is_valid = True
```

❌ **Invalid variable names:**
```python
2nd_place = "Silver"  # Can't start with a number
user-name = "Bob"     # Can't use hyphens
class = "Python"      # Can't use reserved words
```

### Naming Best Practices

1. **Use descriptive names:** `student_count` not `sc`
2. **Use lowercase with underscores:** `first_name` not `FirstName`
3. **Be consistent:** Pick a style and stick with it
4. **Avoid abbreviations:** Unless they're very common (like `id`)

## Data Types

Python has several built-in data types. Here are the most important ones:

### 1. Strings (Text)

Strings are text enclosed in quotes:

```python
# All of these are strings
greeting = "Hello, World!"
name = 'Alice'
message = """This is a
multi-line string"""

# Strings can be combined
first_name = "John"
last_name = "Doe"
full_name = first_name + " " + last_name  # "John Doe"
```

**String Operations:**
```python
text = "Python"

# Length
length = len(text)  # 6

# Uppercase/Lowercase
upper = text.upper()  # "PYTHON"
lower = text.lower()  # "python"

# Repetition
repeated = text * 3  # "PythonPythonPython"
```

### 2. Integers (Whole Numbers)

Integers are whole numbers without decimals:

```python
age = 25
score = 100
year = 2024
negative = -42
```

**Integer Operations:**
```python
# Basic math
sum_result = 5 + 3      # 8
difference = 10 - 4     # 6
product = 6 * 7         # 42
quotient = 20 // 4      # 5 (integer division)
remainder = 17 % 5      # 2 (modulo - remainder)
power = 2 ** 3          # 8 (exponent)
```

### 3. Floats (Decimal Numbers)

Floats are numbers with decimal points:

```python
temperature = 72.5
price = 19.99
pi = 3.14159
```

**Float Operations:**
```python
# Division always returns a float
result = 10 / 4  # 2.5

# Mix integers and floats
mixed = 5 + 2.5  # 7.5

# Rounding
rounded = round(3.14159, 2)  # 3.14
```

### 4. Booleans (True/False)

Booleans represent truth values:

```python
is_student = True
is_raining = False
has_permission = True
```

**Boolean Operations:**
```python
# Comparisons return booleans
is_equal = (5 == 5)          # True
is_greater = (10 > 5)        # True
is_less = (3 < 2)            # False
is_not_equal = (4 != 4)      # False

# Logical operations
both_true = True and True    # True
either_true = True or False  # True
opposite = not True          # False
```

## Type Checking and Conversion

### Check the Type

```python
age = 25
print(type(age))  # <class 'int'>

name = "Alice"
print(type(name))  # <class 'str'>

price = 9.99
print(type(price))  # <class 'float'>
```

### Convert Between Types

```python
# String to integer
age_string = "25"
age_number = int(age_string)  # 25

# Integer to string
score = 100
score_string = str(score)  # "100"

# String to float
price_string = "19.99"
price_number = float(price_string)  # 19.99

# Float to integer (truncates decimal)
temperature = 72.8
temp_int = int(temperature)  # 72
```

## User Input

Make your programs interactive by getting input from users:

```python
# Get user input (always returns a string)
name = input("What is your name? ")
print("Hello, " + name + "!")

# Get numeric input (need to convert)
age_string = input("How old are you? ")
age = int(age_string)
print("Next year you'll be", age + 1)
```

**Tip:** Use AI to help format input prompts nicely!

```python
# Get user's name and greet them properly
```

## F-Strings (Formatted Strings)

F-strings make it easy to combine text and variables:

```python
name = "Alice"
age = 25
city = "New York"

# Old way (harder to read)
message = "My name is " + name + " and I am " + str(age) + " years old."

# F-string way (easier!)
message = f"My name is {name} and I am {age} years old."
print(message)

# Can include expressions
price = 19.99
quantity = 3
print(f"Total: ${price * quantity}")

# Formatting numbers
pi = 3.14159265
print(f"Pi rounded: {pi:.2f}")  # 3.14
```

## Common Operations

### String Formatting

```python
name = "Bob"
score = 95

# Center align
print(f"{name:^20}")  # "        Bob         "

# Right align
print(f"{score:>10}")  # "        95"

# Padding with zeros
print(f"{score:05}")  # "00095"
```

### Math Operations

```python
import math

# Useful math functions
print(math.sqrt(16))    # 4.0
print(math.ceil(4.3))   # 5
print(math.floor(4.9))  # 4
print(abs(-10))         # 10
```

## Hands-On Exercises

### Exercise 1: Personal Info Program

Create a program that:
1. Asks for the user's name
2. Asks for their age
3. Calculates the year they were born (approximately)
4. Prints a summary

```python
# Ask user for their name

# Ask user for their age

# Calculate birth year (2024 - age)

# Print formatted message
```

Expected output:
```
What is your name? Alice
How old are you? 25
Hello Alice! You were born around 1999.
```

### Exercise 2: Simple Calculator

Create a calculator that:
1. Asks for two numbers
2. Performs basic operations
3. Displays results

```python
# Get first number from user

# Get second number from user

# Calculate sum, difference, product, quotient

# Display results in a formatted way
```

### Exercise 3: Temperature Converter

Convert temperature from Fahrenheit to Celsius:
- Formula: C = (F - 32) × 5/9

```python
# Ask user for temperature in Fahrenheit

# Convert to Celsius using formula

# Display result with 1 decimal place
```

### Exercise 4: String Manipulation

Ask for the user's full name and:
1. Count the number of letters
2. Convert to uppercase
3. Convert to lowercase
4. Get their initials

```python
# Get user's full name

# Perform string operations

# Display results
```

### Exercise 5: Shopping Cart

Calculate the total cost of items:
1. Ask for item name
2. Ask for price
3. Ask for quantity
4. Calculate and display total with 15% tax

```python
# Get item details from user

# Calculate subtotal

# Calculate tax (15%)

# Calculate total

# Display formatted receipt
```

## Using AI Assistance

### Good Comment Examples

When working with Copilot, write clear comments:

```python
# Calculate the area of a circle with radius from user input

# Convert temperature from Celsius to Fahrenheit

# Check if a number is even or odd

# Format a phone number as (XXX) XXX-XXXX
```

### Iterating with AI

If the suggestion isn't quite right:

1. **Refine your comment:**
   ```python
   # Convert user input string to integer and handle errors
   ```

2. **Add examples:**
   ```python
   # Convert string to integer
   # Example: "42" -> 42
   ```

3. **Be more specific:**
   ```python
   # Ask user for age, convert to int, then check if age >= 18
   ```

## Common Mistakes and How to Fix Them

### 1. Type Mismatch
```python
# ❌ Wrong
age = input("Age: ")  # age is a string!
next_year = age + 1   # Error: can't add int to string

# ✅ Correct
age = int(input("Age: "))
next_year = age + 1
```

### 2. Forgetting Quotes
```python
# ❌ Wrong
name = Alice  # Python thinks Alice is a variable

# ✅ Correct
name = "Alice"  # Alice is a string
```

### 3. Variable Not Defined
```python
# ❌ Wrong
print(score)  # Error if score doesn't exist yet

# ✅ Correct
score = 100
print(score)
```

### 4. String Concatenation
```python
# ❌ Wrong
age = 25
print("I am " + age)  # Error: can't concatenate int

# ✅ Correct
print("I am " + str(age))
# Or use f-string:
print(f"I am {age}")
```

## Debugging Tips

1. **Print variable values:**
   ```python
   print(f"Debug: age = {age}, type = {type(age)}")
   ```

2. **Check types:**
   ```python
   print(type(variable_name))
   ```

3. **Test with simple values:**
   ```python
   # Use simple test values first
   age = 25  # hardcode value
   # Later, replace with: age = int(input("Age: "))
   ```

## Key Concepts Summary

**Variables:**
- Store information with a name
- Can be reassigned to new values
- Follow naming rules and conventions

**Data Types:**
- **Strings:** Text in quotes
- **Integers:** Whole numbers
- **Floats:** Decimal numbers
- **Booleans:** True or False

**Operations:**
- Math: `+`, `-`, `*`, `/`, `//`, `%`, `**`
- Strings: concatenation (`+`), repetition (`*`)
- Comparison: `==`, `!=`, `<`, `>`, `<=`, `>=`

**User Input:**
- Use `input()` to get user data
- Convert types as needed with `int()`, `float()`, `str()`
- Format output with f-strings

## Reflection Questions

1. When would you use an integer vs. a float?
2. Why do we need to convert input() results?
3. What's the advantage of f-strings over concatenation?
4. How does AI assistance help with variable naming?

## Next Steps

In Lesson 3, you'll learn about:
- If statements (making decisions)
- Comparison operators
- Logical operators
- Building programs that respond to different conditions

## Additional Resources

- [Python Variables - Official Docs](https://docs.python.org/3/tutorial/introduction.html)
- [F-Strings Guide](https://realpython.com/python-f-strings/)
- [Type Conversion in Python](https://realpython.com/python-type-checking/)

---

**Practice Makes Perfect!** Try creating 2-3 small programs using variables and input before moving on. The more you practice, the more natural it becomes!

Ready to continue? Move on to [Lesson 3: Control Flow - Making Decisions](lesson3_control_flow.md)!
