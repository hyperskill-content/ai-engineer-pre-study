# Modules and Imports

Python organizes code into modules (single .py files) and packages (directories containing an `__init__.py` file). The `__init__.py` file can be empty but marks the directory as a Python package. A non-empty one can initialize the package or control what's imported when someone does `from mypackage import *`.

Let's walk through how a module might look like on a small example. Here is a potential project structure:

```
myproject/
├── main.py
└── utils/
    ├── __init__.py       # Empty file
    ├── data_processing.py
    └── formatting.py
```

In `utils/data_processing.py`:

```python
def clean_text(text: str) -> str:
    """Remove extra whitespace and lowercase"""
    return text.strip().lower()

def validate_email(email: str) -> bool:
    """Basic email validation"""
    return '@' in email and '.' in email
```

In `main.py`:

```python
from myproject.utils.data_processing import clean_text, validate_email

# Now you can use the imported functions
user_input = "  Hello@Example.com  "
cleaned = clean_text(user_input)
is_valid = validate_email(cleaned)

print(f"Cleaned: {cleaned}")  # "hello@example.com"
print(f"Valid email: {is_valid}")  # True
```

The import statement tells Python to look in the `myproject` package, find the `utils` package inside it, open the `data_processing` module, and import the specific functions. You import from these using dot notation that mirrors the directory structure.

In general, it's advised to keep related functionality together. For example, functions for data processing in one module, formatting utilities in another, and group related modules into packages like `utils/` or `models/`.