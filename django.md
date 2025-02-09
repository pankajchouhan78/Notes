
### Who developed Django?

Django was initially created by Adrian Holovaty and Simon Willison. They started working on it in 2003 and released the first version of Django in July 2005.

---

### Who developed python?

Python was created by Guido van Rossum, a Dutch programmer. He started working on Python in the late 1980s and released the first version, Python 0.9.0, in February 1991.

---

### Which Companies Uses Django?

Instragram, Spotify, Youtube, Bitbuket, Dropbox.

---

### Which Is the Default Database in Settings File In Django? Sqlite

How do you check the version of Django that you have installed on your system?

You can check the version by opening the command prompt and entering the command: **`Python -m Django --version`**

--------


## Mostly Asked questions:

### 1.  What is Django?
    

Django is a web application framework written in Python programming language. It is based on MVT (Model View Template) design pattern. It follows the "Don't Repeat Yourself" (DRY) principle. Means it reduces redundancy in your code by providing ready-made solutions for common web development tasks like handling databases, user authentication, and routing URLs.

---

### 2.  What Are the Advantages and Disadvantages of Using Django?

**Advantages of Django**:

1. Django provides a lot of built-in features and tools, such as ORM, authentication, forms handling, and admin interface.

2. Django follows the "Don't Repeat Yourself" principle.

3. ORM (Object-Relational Mapping): Django's ORM allows you to interact with your database using Python objects, abstracting away complex SQL queries and making database management easier.

**Disadvantages of Django**:

1. Django's modules are bulky.

2. Django's monolithic size makes it unsuitable for smaller projects

---

### 3. Explain Django Architecture? Also Explain Model, Template and Views.
    
Django architecture consists of:

**Model**: Describe the database schema and data structure.
Structure ko database ki language me schema bolte hai.

**View**: The View is used to execute the business logic and interact with a model to carry data and renders a template.

**Templates**: It defines the layout of a web page.

Mvc me view UI ko represent karta hai or controller User input ko handle karta hai aur model aur view ke beech communication ko manage karta hai.

---

### 4.  What are Django URLs?
In Django, URLs serve as the front door to your online application.
In urls.py, you can configure how Django routing works.

---

### 5.  How does Django handle routing and URL patterns?
Django uses a urls.py file to define URL patterns,
and it uses a URL dispatcher to match requested URLs to the appropriate view functions.

---

### 6.  Discuss Django’s request and response cycle?
Starting the process, the Django server receives a request.
The server then looks for a matching URL in the URL patterns defined for the project.
If the server can’t find a matching URL, it produces 404-status code.
If the server find a matching URL, it executes the corresponding code in the view file associated with the URL and sends a response.

---

### 7. What Is the Difference Between a Project and An App In Django?
| No. | Project | App |
|---- |---------|-----|
| 1.  | A project is the entire Django application. It is a collection of apps. | An app is a module inside the project that is created to perform a specific task. |
| 2.  | **Command To Create a Project:**<br> `django-admin startproject projectname` | **Command To Create an App:**<br> `python manage.py startapp appname` |

---
### 8.  What Is the Difference Between Authentication and Authorization?
| No. | Authentication | Authorization |
|---- |---------------|--------------|
| 1.  | Authentication is the process of verifying the identity of a user. | Authorization is the process of determining what actions or resources an authenticated user is allowed to access. |
| 2.  | It answers the question: **"Who are you?"** | It answers the question: **"What can you do?"** |
| 3.  | Comes **before** authorization. | Comes **after** authentication. |
| 4.  | Typically involves **usernames, passwords, OTPs, or biometric verification**. | Typically involves **role-based access control (RBAC), permissions, and policies**. |
| 5.  | Example: Logging into a website using email & password. | Example: A logged-in user having access to specific pages based on their role (e.g., admin vs. regular user). |

---
### 9. What Is The Difference Between Emp.object.filter(), Emp.object.get() & Emp.objects.all() in Django Queryset?
| No. | Method | Description | Example |
|---- |--------|------------|---------|
| 1.  | **get()** | Used when we want to retrieve a **single unique** object. Raises `DoesNotExist` if no match is found and `MultipleObjectsReturned` if multiple matches exist. | `Users.objects.get(name="Nitin")` |
| 2.  | **filter()** | Used when we want to retrieve **all objects** that match a condition. Returns a QuerySet (which can be empty if no matches are found). | `Users.objects.filter(name="Nitin")` |
| 3.  | **all()** | Used when we want to retrieve **all objects** from the database table. | `Users.objects.all()` |

---

### 10.  Explain The Migration in Django.
Migration is the process of applying changes to the database schema using makemigrations and migrate commands.

Migrations, model classes ke changes ko database me apply karne ke liye ek blueprint ka kaam karte hai.

**Makemigration** - makemigration command is used to create a migration file. it will Actually read our models.py file look for any changes or any modifications and create a migration file. This is Actually the Django’s way of generating the SQL commands.

Syntax: **`python manage.py makemigrations`**

**Migrate** – migrate command creates a table according to the schema defined in migration file. When we run the migrate command, this will execute the SQL commands that are in the migration file.

Syntax: **`python manage.py migrate`**

---

### 11.  Explain the Django project directory structure.
When you create a Django project, Django automatically generates a root directory with the name you give to the project. This root directory contains essential files and folders to provide basic functionality to your web application.

### 12.  What is Django ORM?
Django ORM stands for Object Relational Mapping jo sql query ko replace karte hai, hum datebase me data add modified kar sakte hai without writing sql commands.

Django's ORM allows you to interact with your database using Python objects instead of SQL You can perform various operations such as filtering, updating, and retrieving data from the database.

let's consider a simple SQL query where Employee table to retrieve an employee name.
```
Select * from Employee where name="pankaj";
```
The Equivalent Django ORM query will be:
```
emp = Employee.objects.filter (name="pankaj")
```
Here are some basic examples:
```python
1. Filtering: queryset = MyModel.objects.filter(field_name=value)

2. Get a Single Object: obj = MyModel.objects.get(id=1)

3. Create a new Object: new_obj = MyModel.objects.create(field1=value1)

4. Update an Object:

obj.field = new_value

obj.save()

5. Delete an Object: obj.delete()

```

---

### 13.  What Is a Query-Set in Django? 
QuerySet is a collection of database records.
```python
User.objects.all()

User.objects.filter(name="pankaj")

User.objects.get(id=03)
```
  ---

### 14.  What do you mean by the CSRF Token?
CSRF stands for cross site request forgery, CSRF token is used to prevent the cross-site request forgery attacks.

Django me CSRF token ka use websites ko CSRF attacks se bachane ke liye karte hai. CSRF attacks me, Attackers user ke browser ke through user ke behalf par unauthorized actions perform karne ki koshish karte hai.

---

### 15.  Explain Django Admin & Django Admin Interface.
Django Admin is a built-in, customizable interface for managing data in Django applications. It simplifies administrative tasks, providing automatic CRUD operations and user authentication.

---

### 16.  What Databases are Supported by Django?
Django supports multiple databases. When you start a new Django project, it uses SQLite as the default database.

Here are some of the databases supported by Django:

1. **SQLite**: SQLite is a lightweight, serverless, and file-based relational database. It is the default database used by Django for development purposes due to its simplicity.

2. **PostgreSQL**: PostgreSQL is a powerful open-source object-relational database system. It is known for its advanced features, scalability, and support for complex data types. Many Django projects use PostgreSQL for production environments.

3. **MySQL**: MySQL is another popular open-source relational database management system. It is widely used in web development.

4. **Oracle**: Django supports Oracle databases for larger enterprise-level applications.

---

### 17.  Explain Q objects in Django ORM?
Q objects in Django allow you to perform complex database queries using the logical "OR" and "AND" operations. They provide a way to combine multiple query conditions dynamically, making it more flexible to create complex queries.
```python
from django.db.models import Q

from myapp.models import MyModel  # Query using OR operation with Q objects

queryset = MyModel.objects.filter(Q(name="John") | Q(age=30))

```

In this case, the query-set will contain objects where either the condition name="John" or the condition age=30 is satisfied, and at the same time.

---

### 16.  What Is the Significance Of Settings.py File In Django?
This file, as the name suggests, store our Django project’s configurations or settings, such as database configuration, main URL configurations, backend engine, templating engines, middleware, installed applications, static file addresses, security keys, allowed hosts etc.

---

### 17.  What Is the Significance Of manage.py File In Django?
`manage.py` is a Python script used in Django projects to perform various administrative tasks and manage the project easily. It is automatically created when you start a new Django project.

Some of the tasks you can perform using `manage.py` are:
- You can start the local development server
- You can create new apps
- You can run the migration command

---

### 18.  What are Django-admin and manage.py and explain their commands?
“Django-admin” is the command line utility of Django to perform administrative tasks. And manage.py is created automatically in every Django project. It performs the same functions as Django-admin, but it also modifies the DJANGO SETTINGS MODULE environment variable to point to your project's settings.py file.

---

### 19.  What Is a Middleware in Django?
User interface ki request or response ko handle karne ke liye middle ware ka use karte hai. Pura security iske ander hi hota hai like auth security, session security, csrf security yeh sab middle ware ke ander hi aati hai.

Middleware is a way to process requests globally before they reach the view and responses before they are returned to the browser.

---

### 20.  What is sessions In Django?
Django me sessions ek important feature hai jo web applications me user-specific data ko store karne aur manage karne me madad karta hai.

Sessions in Django are used to store and manage user-specific information across the requests.

Django me sessions ka use authentication, user state management, shopping cart management, me hota hai.

---

### 21.  What Are Django Signals?
django me signals ek powerful mechanism hai jo events-based programming ko support karta hai. Ye events ko capture karne aur ek action ko execute karne ke liye kaam aata hai. Django Signals ek feature hai jo ek hisse ki kisi action ko hone par dusre hisse ko automatically notify karta hai.

Signals Django mein events ko capture karne ke liye use hote hain. Ye decoupled components ko allow karte hain events ke sath interact karne ke liye.

Signals are pieces of code containing information about what is currently going on. A dispatcher is used to both send and listen for signals.

---

### 22.  What is messages framework?
In Django, the "messages framework" is a feature that allows you to store simple messages and display them to the user.

---

### 23.  What Is Context in Django?
In Django, "context" is like a dictionary that carries data for templates. It's a way to store variables in templates and make them available when rendering the template.

---

### 24.  What Is Jinja Templating?
jinja templating is a third-party tool used to create dynamic HTML pages.

---

### 25.  What are Django templates, and how are they different from HTML?
"Django templates are used to generate dynamic HTML content. They are similar to HTML but include template tags for inserting dynamic data from the server.

---

### 26.  What is Django's template inheritance?
Template inheritance allows you to create a base template with common structure and extend it in other templates.

---

### 27.  Define static files and explain their uses.
The word "static files" refers to files in a web app that do not change, such as CSS, JavaScript, or pictures.

Static files woh files hain jo server ke taraf se bina kisi modification ke seedhe client ko serve hoti hain. Ye files mainly include karte hain stylesheets (CSS), JavaScript files, images.

---

### 28.  How does Django handle static files?
Django uses the STATICFILES_DIRS and STATIC_ROOT settings to manage static files.

---

The foreign key is used to link one or more tables together. It is also known as the Referencing Key.

A **Foreign key** is specified as a key that is related to the primary key of another table.

A **Primary key** is used to uniquely identify all table records. You can consider Primary Key constraint to be a combination of UNIQUE and NOT NULL constraint.

The role of the **Unique key** is to make sure that each column and row are unique.
❏  The Unique key cannot accept the duplicate values.
❏  It can accept a null value but only one null value per column

---

### 29.  What Is The Difference Between Django OneToOneField & ForeignKey Field ?
**ForeignKey** is used to create a many-to-one relationship between two models. It is used when one model can have multiple instances related to another model, but each instance of the related model is associated with only one instance of the first model.

Real-Life Example: Socho ek e-commerce application hai jismein humare paas do models hain - `Product` aur `Category`. Har product ek category se associated hai, lekin ek category ke multiple products ho sakte hain.

```python
from  django.db  import  models

class  Category(models.Model):
  name=models.CharField(max_length=100)
 
class  Product(models.Model):
  name=models.CharField(max_length=200)
  category=models.ForeignKey(Category, on_delete=models.CASCADE)
```
  
**OneToOneField** is used to create a one-to-one relationship between two models. It is used when each instance of one model corresponds to exactly one instance of another model.

Real-Life Example: Maan lo, hum ek blogging application banane mein hain jismein humare paas do models hain - `Author` aur `AuthorProfile`. Har author ka ek unique profile hoga, aur har profile sirf ek author se connected hoga. Yahaan, hum `OneToOneField` ka use karenge:
```python
from  django.db  import  models

# First Example:
class  Author(models.Model):
  name=models.CharField(max_length=100)

class  AuthorProfile(models.Model):
  author=models.OneToOneField(Author, on_delete=models.CASCADE)
  bio=models.TextField()
  
 # Second Example:
class Student(models.Model):
  roll_number=models.CharField(max_length=10, unique=True)
  name=models.CharField(max_length=100)
  grade=models.CharField(max_length=5)
  
class StudentProfile(models.Model):
  student=models.OneToOneField(Student, on_delete=models.CASCADE)
  address=models.TextField()
  contact_number=models.CharField(max_length=15)
```

---

### 30.  What is custom user model?
Custom user model ka use karne ka main purpose hota hai Django mein default `User` model ko extend ya modify karna. Default `User` model mein common fields hote hain jaise `username`, `email`, aur `password`. Lekin kai bar aapko apne application ke specific needs ke hisab se aur fields ya functionality ki zarurat hoti hai.

Here are some common reasons for using a custom user model:

Aapko users ke bare mein aur information store karni ho, jaise unka date of birth, profile picture, ya koi aur custom attribute. Custom user model banane se aap apne application ke requirements ke hisab se in fields ko define kar sakte hain.

Aapki authentication requirements default `User` model se alag ho sakti hain. For example, aap email ko primary identifier ke roop mein istemal karna chahte hain. Custom user model se aap authentication ko apne needs ke hisab se design kar sakte hain.

Example: Maan lo, aap ek social networking platform banane mein kaam kar rahe hain. Standard user information ke alawa, aap user ka date of birth, profile picture, aur bio jaise details store karna chahte hain. Custom user model aapko allow karta hai in additional fields ko define karke user ko aapke application ke hisab se represent karna.

---

### 31.  What are the different model inheritance styles in Django?
In Django, there are three types of inheritance.

1.  Abstract base classes -
2.  Multi-table inheritance –
3.  Proxy models -
    
 **Abstract Base Classes** ka use tab hota hai jab aapko kai alag models mein common attributes chahiye hote hain, lekin aap chahte hain ki un common attributes ke liye alag se ek database table na bane.
    
Real-life Example: Socho aap ek blog website bana rahe ho jahan alag-alag cheezein hain jaise articles, comments, aur reviews. Har ek mein common field hongi jaise author_naam, created_at, aur update_at. Ab aap Abstract Base Class ka use karke ye common attributes define kar sakte ho:
```python
class  TimestampedModel(models.Model):
  created_at = models.DateTimeField(auto_now_add=True)
  updated_at = models.DateTimeField(auto_now=True)
  author = models.CharField(max_length=100)

  class Meta:
    abstract = True

  

class Article(TimestampedModel):
  title = models.CharField(max_length=255)
  content = models.TextField()

class Comment(TimestampedModel):
  text = models.TextField()

class Review(TimestampedModel):
  rating = models.IntegerField()
  feedback = models.TextField()
```

**Multi-table Inheritance** ka use tab hota hai jab aapko alag-alag models mein common fields chahiye hote hain, lekin aap chahte hain ki har ek model ke liye alag se ek database table bane. Yeh approach aapko flexibility deti hai alag-alag models ko separately maintain karne mein.

Real-life Example: Let's consider a scenario where you are developing a system for managing different types of products like electronics and books. Har product ke liye kuch common details hain jaise name aur price, lekin har ek product type ke liye kuch specific details bhi hote hain.

```python
class BaseProduct(models.Model):
  name = models.CharField(max_length=255)

  price = models.DecimalField(max_digits=8, decimal_places=2)

class ElectronicProduct(BaseProduct):

  brand = models.CharField(max_length=100)
  warranty_months = models.IntegerField()

class BookProduct(BaseProduct):
  author = models.CharField(max_length=255)
  pages = models.IntegerField()
```

**Proxy Models** ka use tab hota hai jab aapko existing model mein kuch functionality add karni hai, lekin aap database table ko modify nahi karna chahte. Isse aap apne models ko extend kar sakte ho bina unke underlying structure ko change kiye.
  
Real-life Example: Socho aap ek HR management system bana rahe ho jahan aapke paas `Employee` model hai. Ab aap chahte ho ki sirf managers ke liye ek alag view ho jismein unka additional functionality ho, lekin aap original `Employee` model ko alter nahi karna chahte.
```python
class  Employee(models.Model):
  name = models.CharField(max_length=100)
  role = models.CharField(max_length=50)

class  ManagerProxy(Employee):
  class Meta:
    proxy = True

  def  is_manager(self):
    return  self.role == 'Manager'
```  

Yahan, `Employee` ek existing model hai jismein common fields hain. `ManagerProxy` ek proxy model hai jo `Employee` ko extend karta hai. Ismein ek aur method `is_manager` add kiya gaya hai. Isse, managers ke liye specific functionality add ho gayi hai bina asli table ko modify kiye.

---


### 32. Why Django is called lossely coupled framework>
Django is called a loosely coupled framework because of its mvt architecture. which is a variant of the mvc architecture.

---  

### 33. What is Meta class in Django?
A meta class is simply an inner class that provides metadata about the outer class in Django.

---  

### 34.  What Are Generic Views?
"Generic Views Django mein pre-defined views hote hain jo common web development patterns ke liye ready-made solutions provide karte hain. Inka istemal karke hum CRUD (Create, Read, Update, Delete) operations ko asaan taur par implement kar sakte hain bina custom views likhe.
```python
myapp/views.py
from  django.views.generic  import  ListView
from .models  import Book

class  BookListView(ListView):
  model = Book
  template_name = 'book_list.html'
  context_object_name = 'books'
```
---  

### 35.  What is a class-based views in Django?
Django's class-based views (CBVs) are an alternative to function-based views (FBVs) and provide a more object-oriented way to handle HTTP requests.

Now, let's see an example of a simple class-based view in Django:
```python
from  django.views  import  View
from  django.http  import  HttpResponse
from  django.shortcuts  import  render

class  MyView(View):
  template_name = 'my_template.html'  # Template to render

  def  get(self,  request, *args, **kwargs):
    context = {'message':  'Hello from class-based view!'}
    return  render(request, self.template_name, context)

def  post(self,  request, *args, **kwargs):
    Access data from the request, process it, and return a response
    return  HttpResponse('This is a POST request.')
```
  

urls.py
```python
from  django.urls  import  path
from .views import  MyView

urlpatterns = [
path('my-view/', MyView.as_view(), name='my-view'),
]
```
---  

### 36.  What is mixin in django?
Mixin ek programming concept hai jiska istemal code reusability ke liye hota hai. Django mein, Mixin ek class hoti hai jo ek specific functionality ya behavior ko represent karti hai. Yeh class dusri classes ke saath combine ho sakti hai taki unhe woh functionality mil sake.

---

### 37.  Difference between class-based view and function-based view?
Function-Based Views simple functions ka istemal karte hain aur procedural approach follow karte hain, jabki Class-Based Views classes ka istemal karte hain aur object-oriented approach provide karte hain. Function-Based Views asaan views ke liye sahi hain, jabki Class-Based Views complex views ko organize karne mein madad karte hain. Mera preference Class-Based Views ka istemal karna hai kyunki yeh code ko structured taur par rakhta hai aur code reuse ko encourage karta hai.

---

### 38.  What Are Django Exceptions?
Django exceptions aapko errors ko identify aur handle karne mein madad karte hain. Django exceptions are:

1. ValidationError: Form validation errors ke liye raise hoti hai.

2. ObjectDoesNotExist: Jab specific database object retrieve nahi ho pata hai to ye raise hoti hai.

3. ViewDoesNotExist: Agar koi URL ka associated view nahi hota hai to ye raise hoti hai

4. MultipleObjectsReturned: Jab ek specific query se multiple objects return hote hain, jabki aap sirf ek expect karte hain, to ye raise hoti hai.

---
