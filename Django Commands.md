#python 
***
# manage.py commands
[manage.py commands doc](https://docs.djangoproject.com/en/4.2/ref/django-admin/)
- **runserver**: Starts the Django development HTTP server, to serve your Django app on your local computer.
-  **startapp**: Creates a new Django app in your project. We'll talk about what apps are in more depth soon.
-  **shell**: Starts a Python interpreter with the Django settings pre-loaded. This is useful for interacting with your application without having to manually load in your Django settings.
-  **dbshell**: Starts an interactive shell connected to your database, using the default parameters from your Django settings. You can run manual SQL queries in this way.
-  **makemigrations**: Generate database change instructions from your model definitions. You will learn what this means and how to use this command in _Chapter 2_, _Models and Migrations_.
-  **migrate**: Applies migrations generated by the **makemigrations** command. You will use this in _Chapter 2_, _Models and Migrations_, as well.
-  **test**: Run automated tests that you have written. You'll use this command in _Chapter 14_, _Testing_.