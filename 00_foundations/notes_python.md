# Python Fundamentals for BI Developers

## 📌 Why Python?

Python is a powerful and beginner-friendly programming language, widely used in data analysis, data engineering, automation, and AI. It's flexible, readable, and has a rich ecosystem of libraries like `pandas`, `numpy`, `matplotlib`, `scikit-learn`, and `sqlalchemy`.

---

## 🧠 Core Concepts

### Variables & Data Types

```python
name = "Gus"       # String
age = 28           # Integer
is_analyst = True  # Boolean
height = 6.1       # Float
```

---

### Data Structures

- **List**: Ordered, mutable  
- **Tuple**: Ordered, immutable  
- **Set**: Unordered, unique elements  
- **Dict**: Key-value pairs  

```python
fruits = ['apple', 'banana']
colors = ('red', 'green', 'blue')
unique_ids = {101, 102, 103}
user = {'name': 'Gus', 'role': 'Analyst'}
```

---

### Control Flow

```python
if age > 25:
    print("You're experienced.")
elif age == 25:
    print("Quarter-life milestone.")
else:
    print("Fresh blood.")
```

---

### Loops

```python
for fruit in fruits:
    print(fruit)

while age < 30:
    print("Still in your 20s")
    age += 1
```

---

### Functions

```python
def greet(name):
    return f"Hello, {name}!"

print(greet("Gus"))
```

---

## 📊 Working with Data

### Using `pandas`

```python
import pandas as pd

df = pd.read_csv('data.csv')
print(df.head())
df['new_col'] = df['old_col'] * 2
```

---

### Using `sqlalchemy` for SQL

```python
from sqlalchemy import create_engine

engine = create_engine("postgresql://user:password@host/dbname")
df = pd.read_sql("SELECT * FROM my_table", engine)
```

---

## 🛠 Useful Packages

| Use Case           | Library         |
|--------------------|-----------------|
| Data manipulation  | `pandas`        |
| Math & arrays      | `numpy`         |
| Plotting           | `matplotlib`    |
| Machine learning   | `scikit-learn`  |
| Scheduling tasks   | `airflow`       |
| Web apps           | `streamlit`     |
| Querying APIs      | `requests`      |

---

## 🔁 Reusability & Scripts

- Use `.py` files for Python scripts.
- Use `def` to write reusable functions.
- Use `if __name__ == "__main__":` for executable entry points.

---

## ✅ Practice Tips

- Start small: write simple scripts and automate daily BI tasks.
- Refactor frequently: modular, readable code is key.
- Learn to debug with `print()`, `try/except`, and breakpoints.
