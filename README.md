<div id="top"></div>

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]



<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/DhruvaSharma/django_crud.git">
    <img src="images/logo.png" alt="Logo" width="80" height="80">
  </a>

<h3 align="center">Django CRUD operations</h3>

  <p align="center">
    This Project is to demonstrate Create, Read, Update, Delete (CRUD) operations in djnago that follows the model–template–views architectural pattern which is based on MVC architecture.
    <br />
    <a href="https://github.com/DhruvaSharma/django_crud.git"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://invador0007.pythonanywhere.com/employee">View Demo</a>
    ·
    <a href="https://github.com/DhruvaSharma/django_crud/issues">Report Bug</a>
    ·
    <a href="https://github.com/DhruvaSharma/django_crud/issues">Request Feature</a>
  </p>
  <p>
  If demo is not working please raise an issue as pythonanywhere.com turn off free server every 90 days.
  This demo will be disabled on Thursday 27 October 2022.
  </p>
</div>



<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#project-creation-from-scratch">Project creation from scratch</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#references">References</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

[![Product Name Screen Shot][product-screenshot]](https://example.com)

This project demonstrate crud operations via three pages 
* employee form - to create record.
* employee list - to view and update record.
* employee delete - to delete record.

<p align="right">(<a href="#top">back to top</a>)</p>



### Built With

* [![Python][Python]][Python-url]
* [![Django][Django]][Django-url]
* [![MySQL][MySQL]][MySQL-url]
* [![HTML][Html]][Html-url]
* [![CSS][Css]][Css-url]
* [![Bootstrap][Bootstrap]][Bootstrap-url]

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- GETTING STARTED -->
## Getting Started

To get a local copy up and running follow these steps.

Requirements
* virtual environment with dependencies from requirements.txt
* must have a mysql database with following configuration
```sh
DATABASES = {
        'NAME': 'employee_db',
        'USER': 'root',
        'PASSWORD': '12345678',
        }
```
* perform a migrate command at employee_crud/manage.py directory.

```sh
python3 manage.py migrate
```

* run django app.
```sh
python3 manage.py runserver
```

Redirect to view CRUD operations.

http://127.0.0.1:8000/employee/  --> for employee form where new entries are created.

http://127.0.0.1:8000/employee/list  --> to view and delete all the saved entries in database.

## Prerequisites

* Python 3
* pip
* virtual environment
* MySQL
* MySQL connector for python

## Installation

### Python 3
```sh
sudo apt update
```
Install python
```sh
sudo apt install python3
```
Verify python installation
```sh
python3 --version
```

### Pip

```sh
sudo apt update
```
Install pip
```sh
sudo apt install python3-pip
```
Verify pip
```sh
pip3 --version
```

### Virtual Environemnt

```sh
sudo apt-get install build-essential libssl-dev libffi-dev python-dev
```

```sh
sudo apt-get install -y python3-venv
```

### MySQL
```sh
sudo apt update
```
```sh
sudo apt install mysql-server
```
```sh
sudo systemctl start mysql.service
```
refer here for MYSQL configuration : https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-20-04

### MySQL connector

Download package from here : https://dev.mysql.com/downloads/connector/python/

once downloaded install deb package via terminal command 
```sh
sudo dpkg -i name_of_downloaded_file
```


<!-- USAGE EXAMPLES -->
## Project creation from scratch

### Once all the above prerequisites are fulfilled follow further process to create a virtual environment install requirements inside environemnt and create Django CRUD project alongside.
<br>

## Create virtual environemnt and install dependencies

create a directory for project
```python
mkdir django_crud
```

create virtual environemnt
```python
python3 -m venv employee_venv
```

activate virtual environment
```python
source employee_venv/bin/activate
```
when virtual environment is activated it is time to install dependencies which are in requirements.txt
```python
pip3 install -r requirements.txt
```

Next is to create Django project
```python
django-admin startproject employee_crud
```
this will create a directory with same name directory inside it, refer to Project_Structure.md to see and for detailed django project layout refer here: https://data-flair.training/blogs/django-project-layout/ .

To start the newly created Django project change directory to where manage.py resides and run command
```python
python3 manage.py runserver
```
this will start project on http://127.0.0.1:8000/ where you can see the sample Django project running, terminate running project with Ctrl+C and move to model creation ahead.

Now we will create a employee_register app/model to demonstrate CRUD operations in Django for that we will create a employee_register app by following command inside employee_crud.
```python
django-admin startapp employee_register
```
As we have created an app of custom nature we have to include this in settings.py of employee_crud.
Inside employee_crud > settings.py we have
```sh
INSTALLED_APPS = [
                  .............
                ]
```
add  'employee_register', along already listed apps by default and then it looks like.
```sh
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'employee_register',
]
```

Once app is included we also have to define our database inside settings.py for connecting it to MySQL database, which can be done like this.
```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'employee_db',
        'USER': 'root',
        'PASSWORD': '12345678',
        'HOST': '127.0.0.1',
        'PORT': '3306',
    }
}
```
Make sure you have created a database in MySQL before adding database entry in settings.py.

Creating and granting priveleges to database in MySQL or you can do it with GUI like phpmyadmin or MySQL workbench for that install GUI application seperately for now we are sticking to CLI.

Login to mysql with your user
```sql
mysql -u root -p
```
Create a database
```sql
CREATE DATABASE employee_db;
```
Grant all priveleges to user for database.
```sql
GRANT ALL PRIVILEGES ON employee_db.* TO 'root'@'localhost';
```

Next step is to migrate database which is done using command
```
python3 manage.py migrate
```
This will migrate all the default tables to employee_db and you can check to verify by.
```sql
mysql -u root -p
```
```sql
use employee_db;
```
```sql
show tables;
```
So for the next part we will create models for our custom app employee_register, there will be two models Employee and Position.

* /employee_register/models.py
```python
class Position(models.Model):
    title = models.CharField(max_length=50)

    def __str__(self):
        return self.title

class Employee(models.Model):
    fullname = models.CharField(max_length=120)
    emp_code = models.CharField(max_length=3)
    mobile = models.CharField(max_length=10)
    position = models.ForeignKey(Position,on_delete=models.CASCADE)
```

Once code part is done we have to make migrations for these two models.

* /employee_crud/manage.py
```sh
python3 manage.py makemigrations employee_register
```
This will create a new directory named migrations inside employee_register having a 0001_initial.py file which is python representation of models and finally we have to run another command to create tables of these models in mysql database.
```sh
python3 manage.py sqlmigrate employee_register 0001
```
now we finally migrate these tables to mysql database using this command.
```sh
python3 manage.py migrate
```
Verify newly created tables in employee_db database.
```sql
mysql -u root -p
```
```sql
use employee_db;
```
```sql
show tables;
```

Now to handle crud operations we have to have view functions to handle each of the crud requests, we can do that inside view.py inside employee_register app.

```python
from curses.ascii import EM
from multiprocessing import context
from django.shortcuts import redirect, render,redirect 
from .forms import EmployeeForm
from .models import Employee

# Create your views here.

def employee_list(request):
    context = {'employee_list':Employee.objects.all()}
    return render(request,"employee_register/employee_list.html",context)

def employee_form(request,id=0):
    if request.method =="GET":
        if id==0:
            form = EmployeeForm()
        else:
            employee = Employee.objects.get(pk=id)
            form = EmployeeForm(instance = employee)
        return render(request,"employee_register/employee_form.html",{'form':form})
    else:
        if id ==0:
            form = EmployeeForm(request.POST)
        else:
            employee = Employee.objects.get(pk=id)
            form = EmployeeForm(request.POST,instance = employee)
        if form.is_valid():
            form.save()
            return redirect('/employee/list')

def employee_delete(request,id):
    employee = Employee.objects.get(pk=id)
    employee.delete()
    return redirect('/employee/list')
```

First we have to create a url.py file in employee_register directory once done.
We have to configure routing for the employee_register that is done inside urls.py under employee_crud directory.
* /employee_crud/urls.py
```python
from django.contrib import admin
from django.urls import path,include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('employee/', include('employee_register.urls')),

]
```
Now we have to create routes for employee_register regarding crud operations.

```python
from django.urls import path,include
from . import views

urlpatterns = [
    path('', views.employee_form,name='employee_insert'), #get and post req. for insert operation
    path('<int:id>/', views.employee_form,name='employee_update'),  #get and post req. for update operation
    path('list/', views.employee_list,name='employee_list'), #get and post req. to retrieve and display all records
    path('delete/<int:id>', views.employee_delete,name='employee_delete'), #post req. to delete records

]
```
This lead us to create templates to show employee list and form of employee_register app in django, for templates we have to create a directory structure as

<span style="background-color: #6F8FAF"> employee_crud/employee_register/templates/employee_register </sapn> 

*inside templates we have to name the folder same as app name in this case which is employee_register.

Once template directory is ready we will create three tempaltes one as base and other two for form and list on employees.

* base.html
* employee_form.html
* employee_list.html

With template creation now we have to populate its frontend part for which we will use bootstrap.
* /base.html
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Employee Register</title>
    <!-- CSS only -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.0/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-gH2yIJqKdNHPEq0n4Mqa/HGKIhSkIHeL5AyhkYV8i59U5AR6csBvApHHNl/vI1Bx" crossorigin="anonymous">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.1.1/css/brands.min.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.1.1/css/all.min.css">
    <link rel="stylesheet" href="%PUBLIC_URL%/bower_components/font-awesome/css/font-awesome.min.css">
</head>
<body>
    <div class="container">
        <div class="col-md-10 offset-md-1 mt-5">
            <div class="jumbotron bg-light">
                <h1 class="display-4">Employee Register</h1>
                <p class="lead font-italic">Python Django CRUD operations.</p>
                <hr class="my-4">
                {% block content %}
                {% endblock content %}                
              </div> 
        </div>
    </div>


    <!-- JavaScript Bundle with Popper -->
     <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.0/dist/js/bootstrap.bundle.min.js" integrity="sha384-A3rJD856KowSb7dwlZdYEkO39Gagi7vIsF0jrRAoQmDKKtQBHUuLZ9AsSv4jD4Xa" crossorigin="anonymous"></script>
</body>
</html>
```
* /employee_form.html
```html
{% extends "employee_register/base.html" %}
{% load crispy_forms_tags %}

{% block content %}
<!-- <p>Django CRUD operations.</p> -->
<form action="" method="post" autocomplete="off">
    {% csrf_token%}
    {{form.fullname|as_crispy_field}}
    {{form.mobile|as_crispy_field}}
    <div class="row">
        <div class="form-group col-md-6 mb-0">
            {{form.emp_code|as_crispy_field}}
        </div>
        <div class="form-group col-md-6 mb-0">
            {{form.position|as_crispy_field}}
        </div>
    </div>
    <div class="row">
        <div class="col-md-8">
            <button type="submit" class="btn btn-success btn-block btn-lg w-100"><i class="fas fa-save"></i> Submit </button>
        </div>
        <div class="col-md-4">
            <a href="{% url 'employee_list' %}" class="btn btn-secondary btn-block btn-lg w-100">
                <i class="fas fa-stream"></i> Back to list
            </a>
        </div>
    </div>
</form>
{% endblock content %} 
```
* /employee_list.html
```html
{% extends "employee_register/base.html" %}

{% block content %}
<!-- <p>List of employee</p> -->
<table class="table table-borderless">
    <thead class="border-bottom font-weight-bold">
        <tr>
        <td>Full Name</td>
        <td>Mobile</td>
        <td>Position</td>
        <td>
            <a href="{% url 'employee_insert' %}" class="btn btn-outline-success">
                <i class="fas fa-plus"></i> Add New
            </a>
        </td>
        </tr>
    </thead>
    <tbody>
        {% for employee in employee_list %}
        <tr>
        <td>{{employee.fullname}}</td>
        <td>{{employee.mobile}}</td>
        <td>{{employee.position}}</td>
        <td>
            <a href="{% url 'employee_update' employee.id %}" class="btn text-secondary px-0">
                <i class="far  fa-edit fa-lg"></i>
            </a>
            <form action="{% url 'employee_delete' employee.id %}" method="post" class="d-inline">
                {% csrf_token %}
                <button type="submit" class="btn">
                    <i class="far fa-trash-alt fa-lg text-danger float-right"></i>
                </button>
            </form>
        </td>
        </tr>
        {% endfor %}
    </tbody>
</table>
{% endblock content %}
```

After creating templates for the view function add crispy form in settings.py which were installed as requirements of environment.

* /employee_crud/settings.py
```python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'employee_register',
    "crispy_forms",
    "crispy_bootstrap5",
]
```

With this all the coding part is done and now we can test the CRUD operations.

Start the django project

```sh
python3 manage.py runserver
```
Redirect to 

http://127.0.0.1:8000/employee/  --> for employee form where new entries are created.

http://127.0.0.1:8000/employee/list  --> to view and delete all the saved entries in database.



<!-- ROADMAP -->
## Roadmap

- Provide Documentation for Windows

See the [open issues](https://github.com/DhruvaSharma/django_crud.git/issues) for a full list of proposed features (and known issues).

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE` for more information.

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- CONTACT -->
## Contact

Dhruva Sharma - [@twitter_handle](https://twitter.com/Invador0007) - invador0007@gmail.com

Project Link: [https://github.com/DhruvaSharma/django_crud.git](https://github.com/DhruvaSharma/django_crud.git)

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- ACKNOWLEDGMENTS -->
## References
For detailed video refer to video mentioned below.

* [CodAffection](https://www.youtube.com/watch?v=N6jzspc2kds)

For more information about Django.

* https://www.djangoproject.com/
* https://data-flair.training/blogs/django-tutorial/
* https://www.geeksforgeeks.org/django-tutorial/?ref=lbp

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/DhruvaSharma/django_crud?style=for-the-badge
[contributors-url]: https://github.com/DhruvaSharma/django_crud/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/DhruvaSharma/django_crud?style=for-the-badge
[forks-url]: https://github.com/DhruvaSharma/django_crud/network/members
[stars-shield]: https://img.shields.io/github/stars/DhruvaSharma/django_crud?style=for-the-badge
[stars-url]: https://github.com/DhruvaSharma/django_crud/stargazers
[issues-shield]: https://img.shields.io/github/issues/DhruvaSharma/django_crud?style=for-the-badge
[issues-url]: https://github.com/DhruvaSharma/django_crud/issues
[license-shield]: https://img.shields.io/github/license/DhruvaSharma/django_crud?color=%2344CC11&style=for-the-badge
[license-url]: https://github.com/DhruvaSharma/django_crud/blob/main/LICENSE
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/invador0007/
[product-screenshot]: images/screenshot.png
[Python]: https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white
[Python-url]: https://python.org
[Django]: https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white
[Django-url]: https://www.djangoproject.com/
[MySQL]: https://img.shields.io/badge/MySQL-00000F?style=for-the-badge&logo=mysql&logoColor=white
[Mysql-url]: https://www.mysql.com/
[Html]:https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white
[Html-url]: https://html.com/
[Css]: https://img.shields.io/badge/CSS-239120?&style=for-the-badge&logo=css3&logoColor=white
[Css-url]: https://www.w3.org/Style/CSS/Overview.en.html
[Bootstrap]: https://img.shields.io/badge/Bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white
[Bootstrap-url]: https://getbootstrap.com