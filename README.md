# 🛠️ dbt Installation Guide for Windows

A comprehensive guide to installing dbt (data build tool) on Windows with virtual environment setup.

---

## 📋 Prerequisites

Before starting, ensure you have the following:

- **Operating System:** Windows 10 or later
- **Python:** Version 3.7 or higher
- **pip:** Python package manager (included with Python)
- **Data Warehouse:** One of the following:
  - Snowflake
  - Google BigQuery
  - Amazon Redshift
  - PostgreSQL
  - Databricks
- **IDE:** Visual Studio Code (recommended)
- **Version Control:** Git

---

## 🐍 Step 1: Install Python

1. **Download Python**
   - Visit: [https://www.python.org/downloads/windows/](https://www.python.org/downloads/windows/)
   - Download Python 3.7 or higher

2. **Install Python**
   - Run the installer
   - ✅ Check "Add Python to PATH"
   - Click "Install Now"

3. **Verify Installation**
   - In Command Prompt, go to your project folder (e.g., `cd C:\Users\andho\OneDrive\Desktop\dbt test`—create it if needed).
   ```cmd
   python --version


---

## 📦 Step 2: Verify pip Installation

```cmd
pip --version
```

If pip is not found, reinstall Python and ensure "Add Python to PATH" is selected.

---

## 🔧 Step 3: Install virtualenv

```cmd
pip install virtualenv
virtualenv --version
```

---

## 📁 Step 4: Create a Virtual Environment

```cmd
mkdir dbt_project
cd dbt_project
virtualenv dbt-env
```

---

## ✅ Step 5: Activate the Virtual Environment

**For Command Prompt:**
```cmd
cd C:\Users\andho\OneDrive\Desktop\dbt test\dbt_project\dbt-env\Scripts\activate
```

---

## 🚀 Step 6: Install dbt

go to `cd C:\Users\andho\OneDrive\Desktop\dbt test\dbt_project\dbt-env\Scripts`

1. **Install dbt-core**
   ```cmd
   pip install dbt-core
   ```

2. **Install a Database Adapter**

   Choose one based on your data warehouse:

   - **Snowflake**
     ```cmd
     pip install dbt-snowflake
     ```

   - **BigQuery**
     ```cmd
     pip install dbt-bigquery
     ```

   - **Redshift**
     ```cmd
     pip install dbt-redshift
     ```

   - **PostgreSQL**
     ```cmd
     pip install dbt-postgres
     ```

   - **Databricks**
     ```cmd
     pip install dbt-databricks
     ```

> 💡 If installation fails, try:
```cmd
C:\Users\andho\OneDrive\Desktop\dbt test\dbt_project\dbt-env\Scripts>python.exe -m pip install --upgrade pip
```

---

## ✔️ Step 7: Verify dbt Installation

```cmd
dbt --version
```

---

## 🎯 Step 8: Initialize Your First dbt Project

go back 2 folders `cd ..\..` or `cd C:\Users\andho\OneDrive\Desktop\dbt test\dbt_project`

```cmd
dbt init my_project
cd my_project
```

---

## 🔌 Step 9: Configure Database Connection

Edit the `profiles.yml` file located at:

- `C:\Users\andho\OneDrive\Desktop\dbt test\dbt_project\my_project\dbt_project.yml`

Example for Snowflake:
```yaml
my_project:
  target: dev
  outputs:
    dev:
      type: snowflake
      account: your_account
      user: your_username
      password: your_password
      role: your_role
      database: your_database
      warehouse: your_warehouse
      schema: your_schema
      threads: 1
```

---

## 🧪 Step 10: Test your setup

```cmd
dbt debug
```

---

## ▶️ Step 11: Run dbt commands

Use these commands inside your activated virtual environment and dbt project directory.

##  Run dbt Models

```cmd
dbt run
```

Executes all models in your project and materializes them in your data warehouse.

---

##  Run dbt Tests

```cmd
dbt test
```
Runs tests defined in your models to validate data integrity.

---

##  Generate Documentation

```cmd
dbt docs generate
```
Creates documentation files from your dbt project.

---

##  Serve Documentation Locally

```cmd
dbt docs serve
```
Launches a local web server to view your dbt documentation in the browser.

---

##  Deactivate Virtual Environment

```cmd
deactivate
```
Exits the virtual environment and returns to your system Python.


---

## 📚 Additional Resources

- [dbt Documentation](https://docs.getdbt.com/)
- [dbt Community Forum](https://discourse.getdbt.com/)
- [dbt Slack Community](https://www.getdbt.com/community/)

---

## 🐛 Troubleshooting

- **dbt command not found:**
  - Ensure virtual environment is activated
  - Reinstall dbt:
    ```cmd
    pip install --upgrade dbt-core
    ```

- **Connection errors:**
  - Run:
    ```cmd
    dbt debug
    ```
  - Check your `profiles.yml` configuration

---
