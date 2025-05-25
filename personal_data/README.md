# PII Protection & Secure Logging

This Python project demonstrates how to protect **Personally Identifiable Information (PII)** through logging best practices, regex-based data redaction, secure database handling, and password encryption.

---

## Overview

This project includes:

- Regex-based PII data redaction
- Custom `logging.Formatter` to hide sensitive fields
- Logger setup for secure application logging
- Secure MySQL connection using environment variables
- Fetching and filtering user data from a database
- Password encryption using `bcrypt`

---

## Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/Daniel-IRYIVUZE/alu-web_back_end.git
cd personal_data
````

### 2. Create a Virtual Environment

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Required Packages

```bash
pip install bcrypt mysql-connector-python python-dotenv
```

### 4. Configure Environment Variables

Create a `.env` file in the root directory with the following:

```env
PERSONAL_DATA_DB_USERNAME=your_username
PERSONAL_DATA_DB_PASSWORD=your_password
PERSONAL_DATA_DB_HOST=localhost
PERSONAL_DATA_DB_NAME=your_database
```

> **Important:** Do not commit the `.env` file to GitHub.

---

## PII Fields Redacted

The following fields are considered PII (Personally Identifiable Information) and are redacted before logging:

* name
* email
* phone
* ssn
* password

---

## Concepts Demonstrated

* Custom Python logging with sensitive field redaction
* Regex filtering for log sanitization
* Database access with environmental protection
* Password hashing using `bcrypt`

---

## Author

**Daniel Iryivuze**
Software Developer & Content Creator 🇷🇼