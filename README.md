# DJANGO
This is a demo project to explore Django Framework.
https://www.djangoproject.com/

## Install Python
Being a Python Web framework, Django requires Python. Python includes a lightweight database called SQLite so you won’t need to set up a database just yet.
Get the latest version of Python at https://www.python.org/downloads/ or with your operating system’s package manager

## Set up a database
This step is only necessary if you’d like to work with a “large” database engine like PostgreSQL, MySQL, or Oracle.
Django supports many different database servers and is officially supported with PostgreSQL, MySQL, Oracle and SQLite.

In addition to a database backend, you’ll need to make sure your Python database bindings are installed.
- If you’re using PostgreSQL, you’ll need the psycopg2 package. Refer to the PostgreSQL notes for further details.
- If you’re using MySQL, you’ll need a DB API driver like mysqlclient. See notes for the MySQL backend for details.
- If you’re using SQLite you might want to read the SQLite backend notes.
- If you’re using Oracle, you’ll need a copy of cx_Oracle, but please read the notes for the Oracle backend for details regarding supported versions of both Oracle and cx_Oracle.
- If you’re using an unofficial 3rd party backend, please consult the documentation provided for any additional requirements.

**Note:** If you plan to use Django’s manage.py migrate command to automatically create database tables for your models (after first installing Django and creating a project), you’ll need to ensure that Django has permission to create and alter tables in the database you’re using; if you plan to manually create the tables, you can simply grant Django SELECT, INSERT, UPDATE and DELETE permissions. After creating a database user with these permissions, you’ll specify the details in your project’s settings file

## Install Django
Installing an official release with pip is the recommended way to install Django.
1. Install pip
2. Take a look at virtualenv and virtualenvwrapper. These tools provide isolated Python environments, which are more practical than installing packages systemwide. They also allow installing packages without administrator privileges. 
3. After you’ve created and activated a virtual environment, enter the command:
`
  pip install Django
`

## Verifying
To verify that Django can be seen by Python, type python from your shell. Then at the Python prompt, try to import Django:
```
  import django
  print(django.get_version())
  2.2
```
