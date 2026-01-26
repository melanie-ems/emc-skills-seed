# Lesson 4: Loops - Repeating Actions

## Introduction

Imagine you need to print numbers 1 through 100. You could write 100 print statements, but there's a better way: **loops**! Loops let you repeat actions efficiently.

In this lesson, you'll learn how to make your programs do repetitive tasks automatically.

## The For Loop

A `for` loop repeats code a specific number of times:

```python
# Print numbers 1 to 5
for i in range(1, 6):
    print(i)
```

Output:
```
1
2
3
4
5
```

### Understanding range()

The `range()` function generates numbers:

```python
# range(stop) - from 0 to stop-1
for i in range(5):
    print(i)  # Prints: 0, 1, 2, 3, 4

# range(start, stop) - from start to stop-1
for i in range(2, 5):
    print(i)  # Prints: 2, 3, 4

# range(start, stop, step) - with custom step
for i in range(0, 10, 2):
    print(i)  # Prints: 0, 2, 4, 6, 8

# Countdown
for i in range(5, 0, -1):
    print(i)  # Prints: 5, 4, 3, 2, 1
```

### Looping Through Strings

```python
name = "Python"

for letter in name:
    print(letter)
```

Output:
```
P
y
t
h
o
n
```

### Looping Through Lists

```python
fruits = ["apple", "banana", "orange"]

for fruit in fruits:
    print(f"I like {fruit}")
```

Output:
```
I like apple
I like banana
I like orange
```

## The While Loop

A `while` loop repeats as long as a condition is `True`:

```python
count = 1

while count <= 5:
    print(count)
    count += 1  # Same as: count = count + 1
```

Output:
```
1
2
3
4
5
```

### While vs. For

**Use `for` when:**
- You know how many times to repeat
- You're iterating through a collection
- You're counting in a sequence

**Use `while` when:**
- You don't know how many iterations needed
- You're waiting for a condition to change
- You're building an event loop

### Infinite Loops (Be Careful!)

```python
# ⚠️ This loop never ends!
while True:
    print("Forever...")
    # Need a break statement or condition change!

# ✅ Better: Include an exit condition
count = 0
while True:
    print(count)
    count += 1
    if count >= 5:
        break  # Exit the loop
```

## Loop Control Statements

### Break - Exit the Loop

```python
# Find the first negative number
numbers = [10, 20, -5, 30, 40]

for num in numbers:
    if num < 0:
        print(f"Found negative number: {num}")
        break  # Stop the loop
    print(num)
```

Output:
```
10
20
Found negative number: -5
```

### Continue - Skip to Next Iteration

```python
# Print only odd numbers
for i in range(1, 11):
    if i % 2 == 0:
        continue  # Skip even numbers
    print(i)
```

Output:
```
1
3
5
7
9
```

### Else with Loops

The `else` block runs if the loop completes without `break`:

```python
# Search for a value
numbers = [1, 2, 3, 4, 5]
search = 10

for num in numbers:
    if num == search:
        print(f"Found {search}!")
        break
else:
    print(f"{search} not found")
```

Output:
```
10 not found
```

## Nested Loops

Loops inside loops:

```python
# Multiplication table
for i in range(1, 6):
    for j in range(1, 6):
        print(f"{i} × {j} = {i*j}")
    print()  # Blank line after each number
```

### Pattern Printing

```python
# Print a triangle
for i in range(1, 6):
    for j in range(i):
        print("*", end="")
    print()  # New line
```

Output:
```
*
**
***
****
*****
```

## Accumulator Pattern

Use a variable to accumulate results:

```python
# Sum of numbers 1 to 10
total = 0

for i in range(1, 11):
    total += i  # Add to running total

print(f"Sum: {total}")  # 55
```

### Counting Pattern

```python
# Count vowels in a string
text = "Hello World"
vowel_count = 0

for char in text.lower():
    if char in "aeiou":
        vowel_count += 1

print(f"Vowels: {vowel_count}")  # 3
```

### Building a List

```python
# Create a list of squares
squares = []

for i in range(1, 6):
    squares.append(i ** 2)

print(squares)  # [1, 4, 9, 16, 25]
```

## List Comprehensions (Bonus!)

A compact way to create lists:

```python
# Traditional way
squares = []
for i in range(1, 6):
    squares.append(i ** 2)

# List comprehension way
squares = [i ** 2 for i in range(1, 6)]

print(squares)  # [1, 4, 9, 16, 25]
```

With conditions:
```python
# Only even squares
even_squares = [i ** 2 for i in range(1, 11) if i % 2 == 0]
print(even_squares)  # [4, 16, 36, 64, 100]
```

## Real-World Examples

### Example 1: Password Attempts

```python
# Allow 3 login attempts
max_attempts = 3
correct_password = "python123"

for attempt in range(max_attempts):
    password = input(f"Enter password (attempt {attempt + 1}/{max_attempts}): ")
    
    if password == correct_password:
        print("✓ Login successful!")
        break
    else:
        remaining = max_attempts - attempt - 1
        if remaining > 0:
            print(f"✗ Wrong password. {remaining} attempts remaining.")
else:
    print("✗ Account locked. Too many failed attempts.")
```

### Example 2: Menu System

```python
# Simple menu loop
while True:
    print("\n=== Menu ===")
    print("1. Say Hello")
    print("2. Tell Joke")
    print("3. Exit")
    
    choice = input("Choose an option: ")
    
    if choice == "1":
        name = input("What's your name? ")
        print(f"Hello, {name}!")
    elif choice == "2":
        print("Why did the programmer quit? Because they didn't get arrays!")
    elif choice == "3":
        print("Goodbye!")
        break
    else:
        print("Invalid choice. Please try again.")
```

### Example 3: Number Guessing Game

```python
import random

# Generate random number
secret = random.randint(1, 100)
attempts = 0
max_attempts = 7

print("I'm thinking of a number between 1 and 100!")

while attempts < max_attempts:
    guess = int(input(f"Guess #{attempts + 1}: "))
    attempts += 1
    
    if guess == secret:
        print(f"🎉 Correct! You won in {attempts} attempts!")
        break
    elif guess < secret:
        print("📈 Too low!")
    else:
        print("📉 Too high!")
    
    remaining = max_attempts - attempts
    if remaining > 0:
        print(f"({remaining} guesses left)")
else:
    print(f"😞 Game over! The number was {secret}")
```

### Example 4: Statistics Calculator

```python
# Calculate statistics for a list of numbers
numbers = []

print("Enter numbers (type 'done' when finished):")

while True:
    user_input = input("Number: ")
    
    if user_input.lower() == "done":
        break
    
    try:
        number = float(user_input)
        numbers.append(number)
    except ValueError:
        print("Please enter a valid number or 'done'")

if numbers:
    print(f"\n=== Statistics ===")
    print(f"Count: {len(numbers)}")
    print(f"Sum: {sum(numbers)}")
    print(f"Average: {sum(numbers) / len(numbers):.2f}")
    print(f"Min: {min(numbers)}")
    print(f"Max: {max(numbers)}")
else:
    print("No numbers entered!")
```

## Hands-On Exercises

### Exercise 1: Countdown Timer

Create a countdown from 10 to 1, then print "Blast off!"

```python
# Create countdown using a for loop
```

### Exercise 2: Times Table

Ask the user for a number and print its multiplication table (1-10).

```python
# Get number from user

# Print multiplication table
```

### Exercise 3: FizzBuzz

Classic programming challenge! Print numbers 1-30, but:
- For multiples of 3, print "Fizz"
- For multiples of 5, print "Buzz"
- For multiples of both, print "FizzBuzz"

```python
# Implement FizzBuzz
```

### Exercise 4: Sum Calculator

Keep asking for numbers until the user types "done", then show the total.

```python
# Initialize total

# Loop until user says done

# Display result
```

### Exercise 5: Palindrome Checker

Check if a word reads the same forwards and backwards.

```python
# Get word from user

# Check if palindrome using a loop

# Print result
```

### Exercise 6: Pattern Generator

Ask the user for a number and print this pattern:
```
n = 5
1
2 2
3 3 3
4 4 4 4
5 5 5 5 5
```

```python
# Get number from user

# Generate pattern with nested loops
```

### Exercise 7: Prime Number Checker

Check if a number is prime (only divisible by 1 and itself).

```python
# Get number from user

# Check if prime using a loop

# Print result
```

### Exercise 8: Shopping List

Create a shopping list program that:
- Lets user add items
- Shows all items
- Lets user remove items
- Exits when user chooses

```python
# Initialize empty list

# Main menu loop
```

## Using AI with Loops

### Good Prompts for Copilot

```python
# Generate Fibonacci sequence up to n terms

# Find all factors of a number

# Reverse a string using a loop

# Calculate factorial using a loop

# Remove duplicates from a list
```

### Debugging Loop Issues

When Copilot suggests a loop:
1. Check the range/condition - will it ever end?
2. Verify the loop variable is updated properly
3. Test with small examples (e.g., range(3) before range(1000))
4. Check off-by-one errors (should it be `n` or `n+1`?)

## Common Mistakes

### 1. Off-by-One Errors

```python
# ❌ Prints 0-4 (only 5 numbers)
for i in range(5):
    print(i)

# ✅ Prints 1-5 (5 numbers)
for i in range(1, 6):
    print(i)
```

### 2. Infinite Loops

```python
# ❌ Never ends!
count = 0
while count < 5:
    print(count)
    # Forgot to increment count!

# ✅ Ends properly
count = 0
while count < 5:
    print(count)
    count += 1
```

### 3. Modifying List While Iterating

```python
# ❌ Problematic
numbers = [1, 2, 3, 4, 5]
for num in numbers:
    if num % 2 == 0:
        numbers.remove(num)  # Don't do this!

# ✅ Better: Create new list
numbers = [1, 2, 3, 4, 5]
odd_numbers = [num for num in numbers if num % 2 != 0]
```

### 4. Wrong Loop Type

```python
# ❌ Using while when for is clearer
i = 0
while i < 5:
    print(i)
    i += 1

# ✅ Better: Use for loop
for i in range(5):
    print(i)
```

## Debugging Loops

### Add Print Statements

```python
for i in range(5):
    print(f"Debug: i = {i}")  # See what i is
    # Your code here
```

### Test with Small Numbers

```python
# Start small to verify logic
for i in range(3):  # Test with just 3
    print(i)

# Then scale up
for i in range(100):  # Now use 100
    print(i)
```

### Check Loop Conditions

```python
count = 0
while count < 5:
    print(f"Before: count = {count}")
    # Your code
    count += 1
    print(f"After: count = {count}")
```

## Key Concepts Summary

**For Loops:**
- Repeat a specific number of times
- Iterate through collections
- Use `range()` for numbers

**While Loops:**
- Repeat while condition is True
- Good for unknown iterations
- Watch for infinite loops!

**Loop Control:**
- `break`: Exit loop early
- `continue`: Skip to next iteration
- `else`: Runs if loop completes normally

**Patterns:**
- Accumulator: Build up a value
- Counter: Count occurrences
- Search: Find specific items
- Generator: Create new collections

## Reflection Questions

1. When would you choose a `while` loop over a `for` loop?
2. What's the purpose of the `break` statement?
3. How can you avoid infinite loops?
4. What's an accumulator pattern and when is it useful?

## Next Steps

In Lesson 5, you'll learn about:
- Functions (organizing reusable code)
- Parameters and return values
- Scope and namespaces
- Built-in functions

## Additional Resources

- [Python For Loops - Official Docs](https://docs.python.org/3/tutorial/controlflow.html#for-statements)
- [While Loops in Python](https://realpython.com/python-while-loop/)
- [Loop Better](https://realpython.com/python-for-loop/)

---

**Practice Challenge:** Create a text-based RPG battle system where the player and enemy take turns attacking until one reaches 0 health!

Ready to continue? Move on to [Lesson 5: Functions - Reusable Code](lesson5_functions.md)!
