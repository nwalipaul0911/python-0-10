# Week 0: Your First Steps with Python

Welcome! This week is for learners who are completely new to programming. You do not need any previous coding experience. The goal is to learn how to give a computer instructions in Python and build confidence by trying small examples.

After this lesson, continue with [Week 1](../week%201/lesson.md), where you will learn Python's core collection types.

## What is programming?

A computer follows instructions. A **program** is a set of instructions written in a language the computer can run. Python is a programming language designed to be readable by people.

Programming is not about guessing the perfect answer immediately. It is about:

1. Understanding what you want the computer to do.
2. Breaking the task into small steps.
3. Writing those steps in Python.
4. Running the program and checking what happened.
5. Fixing and improving it when needed.

An error is not a failure; it is information that helps you find what to correct.

## Set up your working environment

You need Python and a place to write and run it. One beginner-friendly setup is:

1. Install a current stable version of Python 3 from [python.org](https://www.python.org/downloads/).
2. Install a code editor such as Visual Studio Code.
3. In the editor, install the Python and Jupyter extensions.
4. Create a folder for your weekly lessons and open that folder in the editor.
5. Create or open a `.ipynb` notebook, select a Python interpreter/kernel, and run a code cell.

You can also write regular `.py` Python files. For this course, notebooks are useful because they let you run small pieces of code one cell at a time. A notebook has **Markdown cells** for notes and **code cells** for Python. Run a code cell with its Run button; the output appears underneath. If the editor asks you to choose a kernel or interpreter, choose the Python 3 environment you installed.

Keep your weekly files together and give them clear names. Save your work often. If a cell seems to use an old value, run the cells that define its variables first.

### Comments and indentation

Python ignores text after `#` on a line; this is a **comment** for people reading the code:

```python
# This line explains the next instruction.
print("Comments do not run")
```

Indentation groups instructions into blocks. Use four spaces for each indentation level and keep the indentation consistent.

## 1. Your first instruction: `print`

`print()` displays information:

```python
print("Hello, Python!")
print(2 + 3)
```

Text goes inside quotation marks. A number does not need quotation marks. The parentheses tell Python what information to print.

You can print more than one item by separating them with commas:

```python
name = "Mina"
print("Hello", name)
```

## 2. Values and variables

Programs work with **values**. Common beginner value types include:

| Type | What it represents | Example |
|---|---|---|
| Integer (`int`) | Whole numbers | `7`, `-2` |
| Decimal (`float`) | Numbers with a decimal point | `3.5`, `-0.25` |
| String (`str`) | Text | `"hello"`, `'Python'` |
| Boolean (`bool`) | True or false | `True`, `False` |

A **variable** is a name that refers to a value. Use `=` to assign a value to a variable:

```python
age = 12
student_name = "Mina"
has_started = True

print(student_name)
print(age + 1)
```

The `=` sign means “store the value on the right under the name on the left.” It does not mean “is equal to” as it does in a math equation. To compare two values, use `==`.

Choose names that explain what a value means. Python variable names are case-sensitive, so `score` and `Score` are different names. Use underscores instead of spaces, such as `total_points`.

### Updating variables

The assignment operator `=` gives a variable a value. You can assign a new value later:

```python
score = 10
score = score + 5
print(score)  # 15
```

The shorter form `score += 5` means the same thing as `score = score + 5`. Similar forms include `-=`, `*=`, and `/=`. These are **augmented assignment operators**: they update a variable using its current value.

## 3. Arithmetic and expressions

Python can calculate with numbers:

```python
print(8 + 3)   # addition: 11
print(8 - 3)   # subtraction: 5
print(8 * 3)   # multiplication: 24
print(8 / 3)   # division: 2.666...
print(8 // 3)  # whole-number division: 2
print(8 % 3)   # remainder: 2
print(2 ** 3)  # power: 8
```

An **expression** is a piece of code Python can evaluate to produce a value. For example, `price * quantity` is an expression:

```python
price = 4
quantity = 3
cost = price * quantity
print(cost)  # 12
```

Use parentheses to make the order of a calculation clear:

```python
print((2 + 3) * 4)  # 20
```

## 4. Text and numbers from input

You can join strings with `+`:

```python
first_name = "Mina"
greeting = "Hello, " + first_name
print(greeting)
```

The `input()` function asks the person running a program to type something. Its result is always text (`str`), even if the person types digits:

```python
name = input("What is your name? ")
print("Hello, " + name)
```

To do arithmetic with typed input, convert it to a number:

```python
age_text = input("How old are you? ")
age = int(age_text)
print(age + 1)
```

Use `int()` for whole numbers and `float()` for decimal numbers. If the typed text is not a valid number, Python will show an error; for now, type a valid number when asked.

## 5. Making decisions with `if`

A **condition** is an expression that is either `True` or `False`. An `if` statement lets a program choose what to do:

```python
temperature = 28

if temperature > 25:
    print("It's a warm day.")
else:
    print("It's not very warm.")
```

The indented lines belong to the `if` or `else` block. In Python, indentation is part of the syntax, so use consistent indentation (four spaces is the usual convention).

Comparison operators:

| Operator | Meaning |
|---|---|
| `==` | equal to |
| `!=` | not equal to |
| `>` | greater than |
| `<` | less than |
| `>=` | greater than or equal to |
| `<=` | less than or equal to |

Use `elif` to check another condition:

```python
score = 72

if score >= 90:
    print("Great job!")
elif score >= 60:
    print("You passed.")
else:
    print("Keep practicing.")
```

### Combining conditions

Use `and`, `or`, and `not` to combine or reverse conditions:

```python
age = 15
has_permission = True

if age >= 13 and has_permission:
    print("Both conditions are true")

if age < 13 or not has_permission:
    print("At least one condition is true")
```

- `and` is true only when both sides are true.
- `or` is true when at least one side is true.
- `not` reverses `True` and `False`.

Use parentheses to make longer conditions easier to read. Compare values with `==`, not `=`: `=` assigns a value, while `==` asks whether two values are equal.

## 6. Repeating instructions with loops

A loop repeats instructions. A `for` loop can go through a sequence of numbers produced by `range()`:

```python
for number in range(4):
    print(number)
```

This prints `0`, `1`, `2`, and `3`. The ending number is not included. To count from `1` through `4`, use `range(1, 5)`:

```python
for number in range(1, 5):
    print(number)
```

You can also repeat over each character in text:

```python
for letter in "cat":
    print(letter)
```

Each line inside the loop is run once for each item. Be careful to indent the instructions that should repeat.

## 7. Functions: reusable instructions

A **function** is a named group of instructions. Define it with `def`, give it a name, and put any needed inputs between parentheses:

```python
def greet(name):
    print("Hello, " + name)

greet("Mina")
```

The value passed into the function is called an **argument**. In the example, `"Mina"` is passed to the function and is available inside it through the parameter `name`.

Use `return` when a function should give a result back to the code that called it:

```python
def double(number):
    return number * 2

answer = double(5)
print(answer)  # 10
```

`print()` displays something for a person to see. `return` sends a result back so the program can use it later.

## 8. Reading errors and debugging

If Python cannot run code, it displays an error message. Read the last line first to see the kind of error, then look at the line number and code nearby.

Common beginner mistakes include:

- Missing a closing quote or parenthesis.
- Misspelling a variable or function name.
- Using text where a number is needed.
- Forgetting the colon after `if`, `else`, `elif`, `for`, or `def`.
- Indenting a line incorrectly.

Change one thing at a time, then run the code again. Small experiments are a good way to learn.

## How to practice

Open [the Week 0 practice notebook](./python_basics_practice.ipynb). Run each example, then try the exercises in order. The exercise cells are intentionally left for you to complete. When you have practiced the concepts, finish the separate [Week 0 problem set](./problem_set.ipynb).

When stuck:

1. Read the task again and identify the expected input and output.
2. Try a tiny example by hand.
3. Write one small step at a time.
4. Run the code and inspect the output or error.
5. Ask for help with the specific line or idea that is confusing.

## Ready for Week 1?

Before moving on, make sure you can:

- Open a Python notebook, select a kernel, and run a code cell.
- Run a code cell and use `print()`.
- Store values in variables, recognize common data types, and convert typed input into a number.
- Use arithmetic and augmented assignment.
- Compare values and combine conditions with `and`, `or`, and `not`.
- Write a simple `if` / `elif` / `else` statement.
- Use a `for` loop to repeat an instruction.
- Define a function and return a result.

You do not need to memorize everything. You can return to this lesson whenever you need a reminder. Week 1 introduces lists, tuples, dictionaries, and sets.
