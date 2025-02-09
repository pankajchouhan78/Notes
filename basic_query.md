
## Query-set Based Question:

### 1. What Is the Command to Install Django & To Know About It’s Version?

- Command To Install Django: **`pip install django`**
- Command To Check Django Version: **`python -m django --version`**
- Command To Check all the versions of installed modules: **`pip freeze`**

  
### 2. What Is the Command to Create A Project & An App In Django?

- Command To Create a Project: **`django-admin startproject nitman`**
- Command To Create an App: **`python manage.py startapp nitapp`**

where nitman is project name & nitapp is app name.

### 3. What Is the Command to Run A Project In Django?

- Command To Run a Project: **`python manage.py runserver`**

By default, this command starts the development server on the internal IP at port 8000.
- If you want to change the server's port, **`python manage.py runserver 8080`**
- If you want to change the server's IP, use: **`python manage.py runserver 0.0.0.0:8000`**

### 4. What Is the Command used For Migrations In Django?

- Command to create a migration file inside the migration folder:
**`python manage.py makemigrations`**

After creating a migration, to reflect changes in the database permanently execute migrate command: **`python manage.py migrate`**

To see all migrations, execute the command: **`python manage.py showmigrations`**
To see app-specific migrations by specifying app-name, execute the command:
**`python manage.py showmigrations nitapp`**

  
### 5. What Is the Command To Create A Superuser In Django?

Command To Create a super-user: **`python manage.py createsuperuser`**

### 6. How To View All Items In the Model Using Django Query-Set?

- Django Command To View All Items In A Model: **`Users.objects.all()`**

where “User” is a model name

### 7. How To Filter Items In the Model Using Django QuerySet?

Django Command To Filter Items In A Model: **`Users.objects.filter(name="Nitin")`**

where “User” is a model name.


### 8. How To Get A Particular Item In The Model Using Django QuerySet?

- Django Command To Get A Particular Item In A Model: Users.objects.get(id=25)
where “User” is a model name.  

### 9. How to Delete/Insert/Update an Object Using QuerySet In Django?

- QuerySet To Delete An Object: **`Users.objects.filter(id= 54).delete()`**
- QuerySet To Update an Object:
user_to_be_modify = User.objects.get(pk = 3)
user_to_be_modify.city = "Pune"
user_to_be_modify.save()

- QuerySet To Insert/Add an Object:
new_user = User(name = "Nitin Mangotra", city="Gurgaon")
new_user.save()
