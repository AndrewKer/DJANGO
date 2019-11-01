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
  `pip install mysqlclient`
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
Or...
```
  py -m django --version
```
# Writing your fist Django app

## Creating a project
If this is your first time using Django, you’ll have to take care of some initial setup. Namely, you’ll need to auto-generate some code that establishes a Django project – a collection of settings for an instance of Django, including database configuration, Django-specific options and application-specific settings.

From the command line, cd into a directory where you’d like to store your code, then run the following command:
```
  django-admin startproject mysite
```
This will create a *mysite* directory in your current directory.

>**Note:** It’s not a good idea to put any of this Python code within your Web server’s document root, because it risks the possibility that people may be able to view your code over the Web. That’s not good for security.Put your code in some directory outside of the document root, such as /home/mycode.

Let’s look at what startproject created:
```
mysite/
    manage.py
    mysite/
        __init__.py
        settings.py
        urls.py
        wsgi.py
```
These files are:

 - The outer **mysite/** root directory is just a container for your project. Its name doesn’t matter to Django; you can rename it to anything you like.
 - **manage.py**: A command-line utility that lets you interact with this Django project in various ways.
 - The inner **mysite/** directory is the actual Python package for your project. Its name is the Python package name you’ll need to use to import anything inside it (e.g. mysite.urls).
 - **mysite/__init__.py**: An empty file that tells Python that this directory should be considered a Python package. If you’re a Python beginner, read more about packages in the official Python docs.
 - **mysite/settings.py**: Settings/configuration for this Django project. Django settings will tell you all about how settings work.
 - **mysite/urls.py**: The URL declarations for this Django project; a “table of contents” of your Django-powered site.
 - **mysite/wsgi.py**: An entry-point for WSGI-compatible web servers to serve your project.

## Activating models

To include the app in our project, we need to add a reference to its configuration class in the **INSTALLED_APPS** setting.
Edit the **mysite/settings.py** file and add that dotted path to the **INSTALLED_APPS** setting.

```
 python manage.py makemigrations polls
```

By running makemigrations, you’re telling Django that you’ve made some changes to your models (in this case, you’ve made new ones) and that you’d like the changes to be stored as a migration.

Migrations are how Django stores changes to your models (and thus your database schema) - they’re just files on disk.