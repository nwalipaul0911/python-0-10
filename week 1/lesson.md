# Week 1: Python Collections

This week introduces four ways to group information: **lists**, **tuples**, **dictionaries**, and **sets**. Each collection is useful for a different kind of task. By the end of the week, you should be able to choose a suitable collection, read and update it, and loop through its contents.

After working through the lesson and examples, complete the [Week 1 problem set](./problem_set.ipynb). The [cumulative distance notebook](./cumulative_distance_problem.ipynb) contains worked examples for optional extra practice with collections and position-based reasoning.

## Learning goals

- Create and access lists and tuples.
- Understand indexes, list operations, and list mutability.
- Store named information in dictionaries.
- Collect unique values and compare groups with sets.
- Choose a collection based on what information needs to be stored.
- Loop through collection items and test whether an item is present.

## 1. Lists: ordered, changeable collections

A **list** stores items in order. Lists can contain repeated values and can be changed after they are created.

```python
colors = ["red", "blue", "green", "blue"]
print(colors)
```

### Reading items and indexes

Python indexes start at `0`. Negative indexes count backward from the end:

```python
print(colors[0])   # red
print(colors[1])   # blue
print(colors[-1])  # blue, the last item
```

Use `len()` for the number of items. A slice selects part of a list; the end index is excluded:

```python
numbers = [10, 20, 30, 40, 50]
print(len(numbers))  # 5
print(numbers[1:4])  # [20, 30, 40]
```

### Changing lists

```python
colors[0] = "purple"       # replace an item
colors.append("orange")    # add one item to the end
colors.remove("blue")     # remove the first matching item
last_color = colors.pop()  # remove and return the last item
```

Use `in` to check whether a value is present:

```python
print("green" in colors)
```

### Looping through a list

Loop over values when you only need each value:

```python
for color in colors:
    print(color)
```

Use `enumerate()` when you need both the index and value:

```python
for index, color in enumerate(colors):
    print(index, color)
```

## 2. Tuples: ordered, fixed collections

A **tuple** is ordered like a list, but it is usually used for a group of values that should stay together and not be changed. Tuples are written with parentheses:

```python
point = (3, 5)
print(point[0])  # 3
x, y = point     # unpack the two values
```

Tuples support indexing, `len()`, and loops. Unlike lists, tuple items cannot be reassigned:

```python
location = ("North", 12)
direction, distance = location
print(direction, distance)
```

Use a tuple for a fixed record such as a coordinate or an RGB color. Use a list when you expect to add, remove, or replace items.

A one-item tuple needs a comma:

```python
single_item = ("hello",)
```

Without the comma, parentheses only group the expression.

## 3. Dictionaries: lookup by key

A **dictionary** stores key-and-value pairs. Use a dictionary when a value has a meaningful name or key:

```python
student = {
    "name": "Ari",
    "grade": 8,
    "enrolled": True,
}

print(student["name"])  # Ari
```

Keys are unique. Assigning to an existing key updates its value; assigning to a new key adds it:

```python
student["grade"] = 9
student["school"] = "Central"
```

Use `.get()` when a key may not exist:

```python
print(student.get("nickname"))             # None
print(student.get("nickname", "not set"))  # not set
```

Loop through keys, values, or key-value pairs:

```python
for key in student:
    print(key)

for key, value in student.items():
    print(key, value)
```

Check for a key with `in`:

```python
if "grade" in student:
    print(student["grade"])
```

## 4. Sets: unique values

A **set** is an unordered collection of unique items. Adding a value that is already present does not create a duplicate:

```python
colors_seen = {"red", "blue", "red"}
print(colors_seen)  # contains red and blue, each once
```

An empty set is written as `set()`; `{}` creates an empty dictionary:

```python
empty_set = set()
```

Add and remove values with `.add()` and `.discard()`:

```python
colors_seen.add("green")
colors_seen.discard("blue")
```

Sets are useful for membership checks and comparing groups:

```python
morning = {"tea", "toast", "fruit"}
afternoon = {"fruit", "sandwich"}

print(morning & afternoon)  # items in both groups
print(morning | afternoon)  # items in either group
print(morning - afternoon)  # items only in morning
```

Use a set when uniqueness matters and you do not need to preserve the items' order. Sets do not support position-based indexing.

## 5. Choosing a collection

| Collection | Ordered? | Changeable? | Duplicates? | Choose it when… |
|---|---|---|---|---|
| `list` | Yes | Yes | Yes | You need an ordered sequence that may change. |
| `tuple` | Yes | No (items cannot be reassigned) | Yes | You need a fixed group of related values. |
| `dict` | In insertion order | Yes | Keys are unique | You need to look up values by meaningful keys. |
| `set` | No positional order | Yes | No | You need unique values or group comparisons. |

## 6. A quick example combining collections

This example stores a list of quiz scores, a tuple for a fixed classroom location, a dictionary for a student's information, and a set of unique club names:

```python
scores = [8, 10, 8]
classroom = ("Building A", 204)
student = {"name": "Ari", "scores": scores}
clubs = {"chess", "robotics", "chess"}

print(student["name"])
print(classroom[1])
print(len(clubs))  # 2 unique clubs
```

The right collection depends on how you will use the data. A list can be stored as a dictionary value, as shown above.

## Problem-solving routine

Before writing code:

1. List the information your program needs to remember.
2. Decide whether order matters.
3. Decide whether the data should change.
4. Decide whether duplicates are allowed.
5. Decide how you will look up an item: by position, by key, or by membership.
6. Try a tiny example by hand before testing your code.

## Ready for the problem set?

You are ready when you can explain why a list and a tuple are different, read a dictionary value by key, and use a set to keep only unique values.

Open the [Week 1 problem set](./problem_set.ipynb) and solve the problems without looking up complete solutions. Some exercises combine collections with loops and functions from Week 0. For optional worked examples, revisit the [cumulative distance notebook](./cumulative_distance_problem.ipynb).
