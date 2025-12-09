<pre>

Step 1: Create the Project
django-admin startproject projectName
cd projectName
python manage.py startapp projectApp

Step 2: Create a View
Inside your project folder (where settings.py and urls.py are located), create a new file named views.py. and add the following code to views.py:
```
from django.http import HttpResponse

def hello_geeks(request):
    return HttpResponse("Hello Geeks")
```
Step 3: Configure URLs
In the urls.py file inside the project folder (projectName/urls.py) and modify it as follows:
1. Import view at the top:
from projectName.views import hello_geeks
2. Add a URL pattern inside the urlpatterns list to link view:

from django.urls import path
from projectName.views import hello_geeks

urlpatterns = [
    path('geek/', hello_geeks),
]

This routes any request to /geek/ to the hello_geeks view.

Step 4: Run the Development Server
Ensure the virtual environment is activated, then start the Django development server:

``` python manage.py runserver ```

In web browse, visit:

http://127.0.0.1:8000/geek/

The message "Hello Geeks" should be displayed.

</pre>
---

