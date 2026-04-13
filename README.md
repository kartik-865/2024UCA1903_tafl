# RE Workbench

A web-based **Regular Expression Workbench** built for the Theory of Automata & Formal Languages (TAFL) course. This tool lets you write regular expressions using an interactive palette, generate all accepted strings, and check equivalence between two regular expressions — all in the browser with no setup required.

---

## Features

### String Generator
- Interactive symbol palette for building regular expressions (quantifiers, operators, alphabet symbols)
- Generates all strings accepted by the given RE up to a configurable max length
- Results displayed as sortable string pills, sorted by length
- Supports `*`, `+`, `?`, `|`, `()`, and `ε` (epsilon)

### Equivalence Checker
- Two separate RE input panels with their own palettes
- Checks whether two regular expressions accept exactly the same language
- Shows **witness strings** — strings that are in one language but not the other — when REs are not equivalent
- Visual `≡` / `≢` verdict with clear explanation

---

## Usage

Just open the live link above. No installation, no dependencies, no internet required after load.

To run locally:
```bash
# Clone the repo
git clone https://github.com/yourusername/re-workbench.git
cd re-workbench

# Serve with Python
python -m http.server 8000
```
Then open `http://localhost:8000` in your browser.

---

## Example Regular Expressions to Try

| RE | Description |
|----|-------------|
| `a(b\|c)*` | Strings starting with `a` followed by any mix of `b` and `c` |
| `(0\|1)*` | All binary strings including empty |
| `a*b+` | Zero or more `a`s followed by one or more `b`s |
| `(ab)+` | One or more repetitions of `ab` |

**Equivalence pairs to test:**
- `(a|b)*` ≡ `(a*b*)*` → **Equivalent**
- `ab*` ≡ `a*b` → **Not Equivalent**

---

## Tech Stack

- Pure **HTML5** — zero frameworks, zero dependencies
- Custom recursive descent **RE parser** built from scratch
- **String enumeration** via AST traversal with BFS-style frontier expansion
- **Equivalence checking** by comparing generated string sets up to a bounded length

---

## Project Structure

```
re-workbench/
└── index.html      # Complete app — single self-contained file
```

---

## Author

**Kartik Gahlot**  
Roll No: `2024UCA1903`  
Subject: Theory of Automata & Formal Languages (TAFL)

---
