# 📄 checkdoc

**checkdoc** is a lightweight Python utility for scanning `.docx` Word documents for specified key phrases. It can be used as a command-line tool or imported as a module in larger projects.

---

## 🔍 Features

- Search for multiple key phrases in `.docx` files
- Scans both paragraphs and tables
- Case-insensitive matching
- Simple CLI interface

---

## 📦 Installation

The recommended usage is with uv:

```bash:
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
uvx checkdoc path/to/document.docx phrase1 phrase2 ...
```

**Example:**

```bash
uvx test.docx "foo" "bar"
```

### As a Module

```python
from checkdoc import find_phrases_in_docx

matches = find_phrases_in_docx("test.docx", ["foo", "bar"])
for line in matches:
    print(line)
```

---

## 🧠 How It Works

- Loads the `.docx` file using `python-docx`
- Scans all paragraphs and table cells
- Matches any text containing the specified phrases (case-insensitive)
- Returns a list of matching text snippets

---

## 🛠 Requirements

- Python 3.13+
- `python-docx`

---

## 📃 License

GNU GPLv3 License. See `LICENSE` file for details.
