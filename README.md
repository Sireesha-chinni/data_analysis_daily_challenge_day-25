# Day 25 – Strings & Tuples (Python Coding Challenge Set)

A set of five beginner-friendly Python challenges focused on cleaning and transforming data stored in tuples using string methods, loops, and sets. The scenarios are based on a student database.

## Challenges and Results

### Challenge 1: Student Name Formatting
Convert inconsistently formatted names to proper case.

```python
students = ("sunitha", "RAVI", "aNu")
```
**Output:** `('Sunitha', 'Ravi', 'Anu')`

**Approach:** loop through the tuple, apply `.capitalize()` to each name, collect the results in a list, then convert it back with `tuple()`.

### Challenge 2: Count Total Subjects
Find the total number of subjects and the number of unique subjects.

```python
subjects = ("Math", "Science", "English", "Math", "Science")
```
**Output:**
```
Total subjects: 5
Unique subjects: 3
```

**Approach:** `len(subjects)` gives the total. Adding every item to a `set` removes duplicates, and the set's length gives the unique count.

### Challenge 3: Remove Extra Spaces from Feedback
Clean unwanted leading and trailing spaces.

```python
feedback = (" good course ", " excellent ", "average ")
```
**Output:** `('good course', 'excellent', 'average')`

**Approach:** apply `.strip()` to each string and rebuild the tuple.

### Challenge 4: Combine Student Name & Course
Join names and courses into `name-course` strings.

```python
names = ("Anu", "Ravi", "John")
courses = ("Python", "SQL", "Power BI")
```
**Output:** `('Anu-Python', 'Ravi-SQL', 'John-Power BI')`

**Approach:** loop with `range(len(names))` and concatenate `names[i] + "-" + courses[i]`. (`zip()` is a shorter alternative.)

### Challenge 5: Extract Email Domains
Pull the domain out of each email address.

```python
emails = ("anu@gmail.com", "ravi@yahoo.com", "john@edu.com")
```
**Output:** `['gmail.com', 'yahoo.com', 'edu.com']`

**Approach:** use `.find("@")` to locate the `@` symbol, then slice the string from the next character onward (`email[ind + 1:]`).

## Concepts Practiced

- Tuple immutability: build a list, then convert back with `tuple()`
- String methods: `capitalize()`, `strip()`, `find()`
- String slicing and concatenation
- Sets for removing duplicates
- `for` loops with direct iteration and with `range(len(...))`
- Built-ins: `len()`, `tuple()`, `set()`

## Files

- `Day-25-Data-analytics-challenge-python.ipynb`: solution notebook
- `Day25_Coding_Challenge.pdf`: original challenge statement

## How to Run

1. Install Python 3.9+ and Jupyter:
   ```bash
   pip install notebook
   ```
2. Launch Jupyter and open the notebook:
   ```bash
   jupyter notebook Day-25-Data-analytics-challenge-python.ipynb
   ```
3. Run the cells from top to bottom (**Kernel → Restart & Run All**).

## Notes and Possible Improvements

- **Challenge 2:** the notebook reassigns `subjects` to the unique tuple, which overwrites the original data. Using a separate variable (e.g. `unique_subjects = set(subjects)`) keeps the original intact. Also, sets are unordered, so the order of unique items may vary between runs.
- **Challenge 5:** the result is a list, while the input is a tuple. Wrapping it in `tuple(domain)` would keep the output type consistent. `email.split("@")[1]` is a compact alternative to `find()` and slicing.
- Most loops can be shortened with generator expressions, for example `tuple(s.strip() for s in feedback)`.
