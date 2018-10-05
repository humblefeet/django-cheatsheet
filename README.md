# django-cheatsheet

## How to create a new Django project
```bash
django-admin startproject projectname
```

## How to start the Django development server
```bash
python3 manage.py runserver
```

## How to create a new application in the project
``` bash
python3 manage.py startapp main_app
```
* main_app is a common name for our app directory

  ### Django Directory Structure
  ```
  djangoproject
  |
  |
  |- djangoproject
  | |
  | |- settings.py: Main settings for project (db, apps, config, etc..)
  | |- url.py: Main URLs for entire project
  | 
  |- application_name
  | |- static: (this is a directory) Holds all static files (css, js, images, aux. forms)
  | |- templates: (this is a directory) Holds all HTML template files
  | |- migrations: (this is a directory) This holds all data migration files
  | |- admin.py: This is where we register data models
  | |- models.py: This is where we put all models
  | |- views.py: This is where we put the functions that run our routes
  | |- urls.py: Every URL for our site is defined here
  |
  |- manage.py: Lets us manage everything about our project
  ```

## How to make URLs with the path() function:
``` python
urlpatterns = [
  path('route/', views.route1_name, name='route_name'),
  path('route/<string_variable>', views.route2_name, name='route2_name'),
  path('route/<int:variable_name>', views.route3_name, name='route3_name'), 
]
```

## How to make a view function:
``` python
def route1_name(request):
  return render(request, 'template.html')

def route2_name(request, string_variable):
  return render(request, 'template2.htmtl', {'data': string_variable})
  
def route3_name(request, variable_name):
return render(request, 'template3.html', {'data': variable_name})
  
