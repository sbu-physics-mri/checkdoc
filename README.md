# 📄 checkdoc

**checkdoc** is a lightweight Python utility for scanning `.docx` Word documents for specified regex patterns. It can be used as a command-line tool or imported as a module in larger projects.

---

## 🔍 Features

- Search for multiple **regex patterns** (supports full Python regex syntax)
- Scans both paragraphs and tables
- Case-insensitive matching by default
- Simple CLI interface

---

## 📦 Installation

The recommended usage is with uv:

```bash
uvx checkdoc
``` 

You can install the required dependencies using pip:

```bash
pip install python-docx
```

or uv:

```bash
uv add checkdoc
```

---

## 🚀 Usage

### Command Line

```bash
uvx checkdoc path/to/document.docx pattern1 pattern2 ...
``` 

**Examples:**

Search for email addresses and phone numbers:
```bash
uvx checkdoc report.docx "\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z|a-z]{2,}\b" "\d{3}-\d{3}-\d{4}"
``` 

Search for any 4-digit year:
```bash
uvx checkdoc contract.docx "\b(19|20)\d{2}\b"
``` 

Search for the exact word "confidential" (not part of other words):
```bash
uvx checkdoc memo.docx "\bconfidential\b"
``` 

### As a Module

```python
from checkdoc import find_phrases_in_docx

# Use raw strings (r"") to avoid escaping issues
matches = find_phrases_in_docx("test.docx", [r"\bemail\b", r"\d{4}"])
for line in matches:
    print(line)
``` 

---

## 🧠 How It Works

- Loads the `.docx` file using `python-docx`
- Scans all paragraphs and table cells
- Uses Python’s `re` module to match **regex patterns** case-insensitively
- Returns matching text snippets (full paragraph/cell content)

---

## 📝 Regex Tips

- Use raw strings (`r"pattern"`) in Python code to avoid backslash escaping issues.
- Patterns are automatically matched case-insensitively.
- Use `\b` for word boundaries to avoid partial matches.
- Use `^` and `$` to match entire lines if needed.
- Test complex patterns with tools like [regex101.com](https://regex101.com) first.

---

## 🛠 Requirements

- Python 3.13+
- `python-docx`

---

## 📃 License

GNU GPLv3 License. See `LICENSE` file for details.
```
