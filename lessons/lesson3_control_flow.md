# Lesson 3: Control Flow - Making Decisions

## Introduction

So far, your programs run from top to bottom, executing every line. But real programs need to make decisions and take different actions based on conditions. This is called **control flow**.

In this lesson, you'll learn how to make your programs smart and responsive!

## The If Statement

An `if` statement lets your program make decisions:

```python
age = 18

if age >= 18:
    print("You are an adult!")
```

**How it works:**
1. Python checks if the condition (`age >= 18`) is `True`
2. If `True`, it runs the indented code
3. If `False`, it skips the indented code

### Indentation Matters!

In Python, indentation (spaces at the start of a line) shows which code belongs to the `if` statement:

```python
if temperature > 80:
    print("It's hot!")        # This runs if condition is True
    print("Stay hydrated!")   # This also runs if condition is True
print("Have a nice day!")     # This ALWAYS runs
```

**Key Rule:** Use 4 spaces for each indentation level (VS Code does this automatically when you press Tab)

## If-Else Statements

What if you want to do something when the condition is `False`?

```python
age = 15

if age >= 18:
    print("You can vote!")
else:
    print("You're too young to vote.")
```

**Flow:**
- If condition is `True` → run the `if` block
- If condition is `False` → run the `else` block
- One or the other, never both!

## If-Elif-Else Statements

For multiple conditions, use `elif` (short for "else if"):

```python
score = 85

if score >= 90:
    print("Grade: A")
elif score >= 80:
    print("Grade: B")
elif score >= 70:
    print("Grade: C")
elif score >= 60:
    print("Grade: D")
else:
    print("Grade: F")
```

**How it works:**
1. Python checks each condition in order
2. Runs the first block where condition is `True`
3. Skips all remaining conditions
4. If no condition is `True`, runs the `else` block (if present)

## Comparison Operators

These operators compare values and return `True` or `False`:

```python
x = 10
y = 5

# Equal to
print(x == y)   # False

# Not equal to
print(x != y)   # True

# Greater than
print(x > y)    # True

# Less than
print(x < y)    # False

# Greater than or equal to
print(x >= 10)  # True

# Less than or equal to
print(y <= 5)   # True
```

**Common mistake:** `=` is assignment, `==` is comparison!

```python
# ❌ Wrong
if age = 18:  # This is assignment!

# ✅ Correct
if age == 18:  # This is comparison
```

## Logical Operators

Combine multiple conditions:

### AND Operator

Both conditions must be `True`:

```python
age = 20
has_id = True

if age >= 18 and has_id:
    print("You can enter!")
else:
    print("Access denied.")
```

Truth table for `and`:
- `True and True` → `True`
- `True and False` → `False`
- `False and True` → `False`
- `False and False` → `False`

### OR Operator

At least one condition must be `True`:

```python
is_weekend = False
is_holiday = True

if is_weekend or is_holiday:
    print("No work today!")
else:
    print("Time to work!")
```

Truth table for `or`:
- `True or True` → `True`
- `True or False` → `True`
- `False or True` → `True`
- `False or False` → `False`

### NOT Operator

Reverses the condition:

```python
is_raining = False

if not is_raining:
    print("Let's go for a walk!")
else:
    print("Stay inside.")
```

### Combining Logical Operators

```python
age = 25
has_license = True
has_car = False

# Can drive if: age >= 18 AND has license AND has car
if age >= 18 and has_license and has_car:
    print("You can drive!")
elif age >= 18 and has_license:
    print("You need a car!")
elif age >= 18:
    print("You need a license and a car!")
else:
    print("You're too young to drive.")
```

Use parentheses for clarity:
```python
if (age >= 18 and has_license) or is_emergency:
    print("Can drive")
```

## Nested If Statements

Put `if` statements inside other `if` statements:

```python
has_ticket = True
age = 15

if has_ticket:
    print("Ticket validated!")
    if age < 12:
        print("Child ticket")
    elif age < 18:
        print("Teen ticket")
    else:
        print("Adult ticket")
else:
    print("Please buy a ticket first!")
```

**Tip:** Don't nest too deeply (3 levels max is usually good). Use logical operators instead when possible.

## Checking Multiple Values

### Membership Testing

Check if a value is in a collection:

```python
vowels = "aeiou"
letter = "a"

if letter in vowels:
    print(f"{letter} is a vowel")

if letter not in vowels:
    print(f"{letter} is not a vowel")
```

### Range Checking

```python
age = 25

# Check if in range
if 18 <= age <= 65:
    print("Working age")

# Equivalent to:
if age >= 18 and age <= 65:
    print("Working age")
```

## Real-World Examples

### Example 1: BMI Calculator

```python
# Get user input
weight = float(input("Enter weight in kg: "))
height = float(input("Enter height in meters: "))

# Calculate BMI
bmi = weight / (height ** 2)

# Determine category
if bmi < 18.5:
    category = "Underweight"
elif bmi < 25:
    category = "Normal weight"
elif bmi < 30:
    category = "Overweight"
else:
    category = "Obese"

print(f"Your BMI is {bmi:.1f} ({category})")
```

### Example 2: Password Validator

```python
# Get password from user
password = input("Create a password: ")

# Check requirements
is_long_enough = len(password) >= 8
has_digit = any(char.isdigit() for char in password)
has_upper = any(char.isupper() for char in password)

# Validate
if is_long_enough and has_digit and has_upper:
    print("✓ Strong password!")
elif is_long_enough:
    print("⚠ Password needs a digit and uppercase letter")
elif has_digit and has_upper:
    print("⚠ Password needs to be at least 8 characters")
else:
    print("✗ Password doesn't meet requirements")
```

### Example 3: Simple Chatbot

```python
# Get user response
response = input("Are you enjoying Python? (yes/no): ").lower()

if response == "yes" or response == "y":
    print("That's great! Keep learning!")
elif response == "no" or response == "n":
    print("Don't give up! It gets easier with practice.")
else:
    print("I didn't understand that. Please answer yes or no.")
```

## Hands-On Exercises

### Exercise 1: Age Classifier

Write a program that asks for someone's age and prints their life stage:
- 0-12: Child
- 13-17: Teenager
- 18-64: Adult
- 65+: Senior

```python
# Get age from user

# Determine and print life stage
```

### Exercise 2: Grade Calculator

Create a program that:
1. Asks for a test score (0-100)
2. Calculates letter grade (A, B, C, D, F)
3. Prints an encouraging message based on grade

```python
# Get score from user

# Calculate letter grade

# Print result with message
```

### Exercise 3: Even or Odd

Write a program that:
1. Asks for a number
2. Determines if it's even or odd
3. Explains how you can tell

Hint: Use the modulo operator (`%`)

```python
# Get number from user

# Check if even or odd using modulo

# Print result
```

### Exercise 4: Login System

Create a simple login that:
1. Asks for username
2. Asks for password
3. Checks against correct values
4. Grants or denies access

```python
correct_username = "admin"
correct_password = "python123"

# Get credentials from user

# Check if both are correct

# Print appropriate message
```

### Exercise 5: Shipping Calculator

Calculate shipping cost based on:
- Orders under $50: $5.99 shipping
- Orders $50-$100: $3.99 shipping
- Orders over $100: Free shipping

```python
# Get order amount from user

# Calculate shipping cost

# Display total with breakdown
```

### Exercise 6: Temperature Comfort

Ask for temperature and determine comfort level:
- Below 60°F: Cold
- 60-70°F: Cool
- 70-80°F: Comfortable
- Above 80°F: Hot

Also check if raining and suggest appropriate clothing.

```python
# Get temperature from user

# Ask if it's raining

# Determine comfort level and suggestions
```

## Using AI for Control Flow

### Good Prompts for Copilot

```python
# Check if a year is a leap year

# Determine if a triangle is valid given three sides

# Check if a string is a palindrome

# Classify a student's performance based on multiple test scores
```

### Understanding AI Suggestions

When Copilot suggests an `if` statement:
1. Check each condition - does it make sense?
2. Trace through with sample values
3. Test edge cases (boundary values)
4. Ensure all possible cases are covered

## Common Mistakes

### 1. Using Assignment Instead of Comparison

```python
# ❌ Wrong
if age = 18:

# ✅ Correct
if age == 18:
```

### 2. Forgetting Colons

```python
# ❌ Wrong
if age >= 18
    print("Adult")

# ✅ Correct
if age >= 18:
    print("Adult")
```

### 3. Incorrect Indentation

```python
# ❌ Wrong
if age >= 18:
print("Adult")  # Not indented!

# ✅ Correct
if age >= 18:
    print("Adult")
```

### 4. Comparing Strings Incorrectly

```python
# ❌ Won't work for "Yes", "YES", etc.
if response == "yes":

# ✅ Better - convert to lowercase first
if response.lower() == "yes":
```

### 5. Using `=` in Conditions

```python
# ❌ Wrong
if 60 <= temperature <= 70:  # Good so far
    if is_raining = True:    # Assignment, not comparison!

# ✅ Correct
if 60 <= temperature <= 70:
    if is_raining:           # Just use the boolean
```

## Debugging Control Flow

### Use Print Statements

```python
age = 25
has_license = True

print(f"Debug: age = {age}, has_license = {has_license}")

if age >= 18 and has_license:
    print("Debug: Condition is True")
    print("Can drive!")
else:
    print("Debug: Condition is False")
```

### Test Each Condition Separately

```python
# Test parts individually
print(f"Age check: {age >= 18}")
print(f"License check: {has_license}")
print(f"Combined: {age >= 18 and has_license}")
```

### Use Simple Test Cases

Start with obvious cases:
```python
# Test with clear True case
age = 20  # Definitely >= 18

# Test with clear False case
age = 10  # Definitely < 18

# Test boundary
age = 18  # Exactly 18
```

## Key Concepts Summary

**Control Flow:**
- `if`: Execute code if condition is True
- `elif`: Check another condition
- `else`: Execute if all conditions are False

**Comparison Operators:**
- `==`, `!=`, `>`, `<`, `>=`, `<=`

**Logical Operators:**
- `and`: Both must be True
- `or`: At least one must be True
- `not`: Reverses the condition

**Best Practices:**
- Use clear, descriptive conditions
- Keep nesting to 2-3 levels max
- Test boundary cases
- Use parentheses for clarity

## Reflection Questions

1. When would you use `elif` vs. nested `if` statements?
2. How does `and` differ from `or`?
3. Why is indentation important in Python?
4. What are edge cases and why should you test them?

## Next Steps

In Lesson 4, you'll learn about:
- Loops (repeating actions)
- `for` loops
- `while` loops
- Loop control (`break`, `continue`)

## Additional Resources

- [Python If...Else - Official Docs](https://docs.python.org/3/tutorial/controlflow.html)
- [Boolean Logic in Python](https://realpython.com/python-boolean/)
- [Python Comparison Operators](https://realpython.com/python-operators-expressions/)

---

**Practice Challenge:** Create a text-based adventure game where the player makes choices and different things happen based on their decisions!

Ready to continue? Move on to [Lesson 4: Loops - Repeating Actions](lesson4_loops.md)!
