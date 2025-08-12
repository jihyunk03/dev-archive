## Generator Expression

A generator expression is similar to a list comprehension, but instead of creating a full list in memory, it creates an iterable **generator object**. This object yields values one by one as they are requested, which makes it highly memory-efficient, especially when dealing with large datasets.

### Syntax
```python
(expression for item in iterable)
````

### Example 1: Squaring Numbers

This example generates the squares of numbers from 0 to 4.

```python
squares_generator = (i * i for i in range(5))

# You can iterate over the generator object to get the values.
for value in squares_generator:
    print(value)
```

**Output:**

```
0
1
4
9
16
```

### Example 2: Cleaning a String

This example shows how to clean a string by filtering out non-alphabetic characters.

```python
string = "iso-gr-am"
cleaned = ''.join(ch for ch in string.lower() if ch.isalpha())
print(cleaned)
```

**Output:**

```
isogram
```

**Explanation:**
The code first converts the string to lowercase using `string.lower()`. Then, it iterates through each character (`ch`) and filters for only those that are alphabetic (`ch.isalpha()`). Finally, the filtered characters are joined back into a new string.