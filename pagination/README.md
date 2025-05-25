# Pagination Project

This project is part of the ALU Web Backend curriculum and focuses on implementing various types of pagination techniques in Python using a dataset of popular baby names. The key goal is to understand how to paginate large datasets effectively, including in deletion-resilient scenarios.

---

## Learning Objectives

By completing this project, you will be able to:

- Implement basic pagination using `page` and `page_size` parameters.
- Add hypermedia metadata to paginated responses.
- Implement pagination that is resilient to deletions.
- Understand RESTful API best practices including HATEOAS principles.

---

## Requirements

- All files are interpreted/compiled with **Python 3.7** on **Ubuntu 18.04 LTS**
- All files must end with a new line
- First line of all Python files: `#!/usr/bin/env python3`
- Use `pycodestyle` (version 2.5.*) for code style compliance
- Each module and function must include a meaningful docstring
- All functions must include **type annotations**
- File: `Popular_Baby_Names.csv` must be used for data

---

## Project Tasks

### 0. Simple helper function

**File:** `0-simple_helper_function.py`

- Function `index_range(page, page_size)` returns a tuple of the start and end index for pagination.
- Page numbers are **1-indexed**.

Example:
```python
index_range(3, 15)  # Output: (30, 45)
````

---

### 1. Simple pagination

**File:** `1-simple_pagination.py`

* Implements a `Server` class that reads from the CSV dataset.
* `get_page(page, page_size)` returns the data rows for the given page.
* Uses `index_range` for calculating the range.
* Includes assertions to validate input.

---

### 2. Hypermedia pagination

**File:** `2-hypermedia_pagination.py`

* Extends `Server` class to implement `get_hyper(page, page_size)`
* Returns a dictionary with:

  * `page_size`
  * `page`
  * `data`
  * `next_page`
  * `prev_page`
  * `total_pages`

Example:

```python
{
  'page_size': 2,
  'page': 1,
  'data': [...],
  'next_page': 2,
  'prev_page': None,
  'total_pages': 9709
}
```

---

### 3. Deletion-resilient hypermedia pagination

**File:** `3-hypermedia_del_pagination.py`

* Adds deletion-resilient pagination via `get_hyper_index(index, page_size)`
* Maintains a dictionary-indexed dataset.
* Handles cases where rows might be deleted between pagination requests.
* Ensures no data is skipped even after deletions.

Returned dictionary includes:

* `index`: starting index of the current page
* `next_index`: index to be used for the next call
* `page_size`: current page size
* `data`: actual data returned

---

## File Structure

```
pagination/
│
├── 0-simple_helper_function.py
├── 1-simple_pagination.py
├── 2-hypermedia_pagination.py
├── 3-hypermedia_del_pagination.py
├── README.md
└── __init__.py (if needed)
```

---

## Usage

To test each task individually:

```bash
$ python3 0-main.py
$ python3 1-main.py
$ python3 2-main.py
$ python3 3-main.py
```

---

## Author

**Daniel Iryivuze**
---

## License

This project is for educational purposes and follows Holberton School’s project guidelines.

```
