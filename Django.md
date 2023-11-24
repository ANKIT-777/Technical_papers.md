
# Django Technical Paper ==>>

## Settings File
Django uses a settings file to configure various aspects of a web application. 
This includes database connection 
- settings 
- time zone
- static files 
- middleware etc.

## Secret Key
The secret key is a cryptographic key used by Django to secure session data, forms, and other cryptographic functions. It should be kept confidential and not shared.

## Default Django Apps
Django includes several default apps such as:
- `django.contrib.admin`: The admin interface.
- `django.contrib.auth`: User authentication.
- `django.contrib.contenttypes`: Content types framework.
- `django.contrib.sessions`: Session framework.
- `django.contrib.messages`: Messaging framework.
- `django.contrib.staticfiles`: Handling static files.

There are more optional apps available and can be added based on project requirements.

## Middleware
Middleware is a way to process requests globally before they reach the view. 
It allows for various functionalities like 
- connection with frontend
- authentication
- security checks

### Security Middleware
- **CSRF (Cross-Site Request Forgery):** Django provides middleware to protect against CSRF attacks by including a hidden input field in forms with a unique token.
- **XSS (Cross-Site Scripting):** Django templates automatically escape variables to prevent XSS attacks.
- **Clickjacking:** Django includes middleware to set the X-Frame-Options header, preventing the site from being embedded in frames.

## Django Security
Django has built-in security measures to address common web application vulnerabilities. 
This includes protection against SQL injection, cross-site scripting, and cross-site request forgery.

## Other Middleware
Apart from security middleware, Django includes other middleware for various purposes like caching, GZip compression, and session handling.

## WSGI (Web Server Gateway Interface)
WSGI is a specification that defines how a web server communicates with web applications. 
Django applications can be deployed using WSGI servers like Gunicorn or uWSGI.


## Django Models File

### `on_delete` Cascade

In Django models, `on_delete` is a parameter used when defining a ForeignKey relationship between two models.
- It specifies the behavior to adopt when the referenced object (the one holding the ForeignKey) is deleted. 
- The `Cascade` option means that when the referenced object is deleted, also delete the objects that have a ForeignKey to it.

Example:
```python
class Author(models.Model):
    name = models.CharField(max_length=100)

class Book(models.Model):
    title = models.CharField(max_length=200)
    author = models.ForeignKey(Author, on_delete=models.CASCADE)
```

In this example, if an `Author` instance is deleted, all associated `Book` instances with that author will also be deleted.

## Fields and Validators
Django provides a variety of fields and validators for modeling different types of data. Some common fields include:
- `CharField`: Used for character fields.
- `IntegerField`: Used for integer fields.
- `DateField`, `DateTimeField`: Used for date and date-time fields.
- `ForeignKey`: Used to create relationships between models.
- `TextField`: Used for large text fields.

Validators are used to ensure data integrity. For example:
- `MaxValueValidator`, `MinValueValidator`: Validate that a value is within a specified range.
- `EmailValidator`: Validate that a value is a valid email address.
- `RegexValidator`: Validate a value against a regular expression.

## Python Module vs. Python Class
- **Python Module:** A Python module is a file containing Python definitions and statements.
- It can define functions, classes, and variables that can be reused in other Python files by importing them.
  Modules are generally used to organize code into logical units.

- **Python Class:** A Python class is a blueprint for creating objects.
- It defines a data structure and methods that operate on that data.
- Instances of a class are objects, and they can have attributes (variables) and methods (functions).
- Classes provide a way to structure and bundle related functionalities.

In Django models, a Python class is used to define a model, representing a database table. 



## Django ORM

### Using ORM Queries in Django Shell
Django provides a powerful Object-Relational Mapping (ORM) system that allows you to interact with your database using Python code rather than raw SQL queries. 
To use ORM queries in the Django shell:

1. Open the Django shell by running `python manage.py shell` in your terminal.
2. Import your models: example `from yourapp.models import YourModel`.
3. Perform queries on your models using the ORM syntax.

Example:
```python
# Importing the model
from yourapp.models import YourModel

# Querying all instances
all_objects = YourModel.objects.all()

# Filtering
filtered_objects = YourModel.objects.filter(some_field='some_value')

# Creating a new instance
new_instance = YourModel.objects.create(some_field='value')
```

### Turning ORM to SQL in Django Shell
You can see the SQL generated by an ORM query in the Django shell by using the `query` method.

Example:
```python
# Import the model
from yourapp.models import YourModel

# Get the queryset
queryset = YourModel.objects.filter(some_field='some_value')

# Print the SQL query
print(queryset.query)
```

### Aggregations
Aggregations in Django refer to the process of performing operations on a set of values and returning a single aggregated result. 
Common aggregations include `count`, `sum`, `avg` (average), `min`, and `max`. These are often used in combination with the `annotate` function to perform calculations on grouped data.

### Annotations
Annotations in Django allow you to add extra information to each object in a queryset. This is often used in conjunction with aggregations. 
For example, you can annotate a queryset with the count of related objects.

Example:
```python
from django.db.models import Count

# Annotate the queryset with the count of related objects
queryset = YourModel.objects.annotate(num_related=Count('related_model'))
```

## Migration File
A migration file in Django is an auto-generated Python script that defines the changes to be made to the database schema.
It includes instructions for creating or modifying tables, columns, indexes, etc. 
Migration files are created using the `makemigrations` management command and are applied to the database using the `migrate` command. 
They are essential for keeping the database schema in sync with the changes in the Django models.

## SQL Transactions
SQL transactions are a way to ensure the atomicity, consistency, isolation, and durability (ACID properties) of database operations. 
A transaction is a sequence of one or more SQL statements executed as a single unit of work. Either all the statements are executed, or none of them is. 
Transactions are used to maintain data integrity and prevent data corruption in case of failures or errors.

## Atomic Transactions
In the context of Django, an atomic transaction is a high-level abstraction that allows you to group multiple database operations into a single transaction block.
If any part of the block fails, the entire block is rolled back, ensuring that the database remains in a consistent state. This is achieved using the `atomic` decorator or the `atomic` context manager.

Example:
```python
from django.db import transaction

@transaction.atomic
def my_function():
    # database operations
    ...
```

This ensures that all operations within `my_function` are treated as a single atomic transaction. If an exception occurs, the entire transaction will be rolled back.


