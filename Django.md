# Searching Hotel Room Project in Django
A fully functional hotel search/filter web app using **Django (Backend)** + **Vue.js (Frontend)**.

This project lets users:

- Sort hotels by price (Ascending / Descending)
- Filter hotels by maximum price using a slider
- See results instantly without reloading the page

## Project Overview
We will build a Django-based hotel search system where Vue.js is used for the frontend to dynamically fetch and display hotel data.

---

## 1. Setup Django Project and App

### Create Django Project
```
django-admin startproject hotel_search
cd hotel_search
```

### Create App
```
python manage.py startapp home
```
Use the Django admin panel at http://127.0.0.1:8000/admin/ to add hotel records.

---

## 2. File Structure

```
hotel_search/
│── hotel_search/
│── home/
│     ├── models.py
│     ├── views.py
│     ├── urls.py
│     ├── admin.py
│     └── templates/
│            └── home.html
└── manage.py
```
Then we need to register app in settings.
<pre>
INSTALLED_APPS = [   
    "django.contrib.admin",
    "django.contrib.auth",
    "django.contrib.contenttypes",
    "django.contrib.sessions",
    "django.contrib.messages",
    "django.contrib.staticfiles",
    "home",
]
</pre>
---

## 3. Define the Hotel Model

```python
from django.db import models

class GFG(models.Model):
    hotel_name = models.CharField(max_length=100)
    hotel_price = models.IntegerField()
    hotel_description = models.TextField()
    created_at = models.DateField(auto_now_add=True)
    updated_at = models.DateField(auto_now=True)

    def __str__(self):
        return self.hotel_name
```

---

## 4. Views (Home & API)

```python
from django.shortcuts import render
from .models import *
from django.http import JsonResponse

def home(request):
    return render(request, 'home.html')

def get_hotel(request):
    try:
        Ans_objs = GFG.objects.all()

        if request.GET.get('sort_by'):
            sort_by_value = request.GET.get('sort_by')
            if sort_by_value == 'asc':
                Ans_objs = Ans_objs.order_by('hotel_price')
            elif sort_by_value == 'dsc':
                Ans_objs = Ans_objs.order_by('-hotel_price')

            if request.GET.get('amount'):
                amount = request.GET.get('amount')
                Ans_objs = Ans_objs.filter(hotel_price__lte=amount)

        payload = []
        for Ans_obj in Ans_objs:
            payload.append({
                'name': Ans_obj.hotel_name,
                'price': Ans_obj.hotel_price,
                'description': Ans_obj.hotel_description,
            })

        return JsonResponse(payload, safe=False)

    except Exception as e:
        print(e)

    return JsonResponse({'message': 'Something went wrong!'})
```

---

## 5. Admin Registration

```python
from django.contrib import admin
from .models import *

class GFGAdmin(admin.ModelAdmin):
    list_display = ['hotel_name', 'hotel_price', 'hotel_description']

admin.site.register(GFG, GFGAdmin)
```

---

## 6. URLs

### Project URLs
```python
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('', include('home.urls')),
    path("admin/", admin.site.urls),
]
```

### App URLs
```python
from .views import *
from django.urls import path

urlpatterns = [
    path('', home),
    path('api/get_GFG/', get_hotel),
]
```

---

## 7. Template (home.html)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Django Hotel Search</title>

    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet">
</head>

<body>
    <div id="app" class="container mt-5 pt-5">
        <h1 class="text-center">GeeksforGeeks</h1>

        <div class="row mt-3">
            <div class="col-md-4">
                <label><strong>Sort By</strong></label>
                <select class="form-control" v-model="selectedSort" @change="sortBy">
                    <option value="asc">ASC</option>
                    <option value="dsc">DSC</option>
                </select>
            </div>

            <div class="col-md-4">
                <label class="form-label"><strong>Select Price</strong></label>
                <input type="range" class="form-range" @change="priceChange($event)"
                       min="1000" max="10000" step="100">
            </div>
        </div>

        <div class="row mt-5 pt-5">
            <div class="col-md-4" v-for="hotel in hotels">
                <div class="card shadow-lg" style="width: 18rem;">
                    <div class="card-body">
                        <h5 class="card-title">[[hotel.name]]</h5>
                        <p class="card-text">[[ (hotel.description).substr(0, 30) ]]</p>
                        <a href="#" class="btn btn-primary">Rs. [[hotel.price]]</a>
                    </div>
                </div>
                <br>
            </div>
        </div>
    </div>

    <script>
        var app = new Vue({
            delimiters: ['[[', ']]'],
            el: '#app',
            data: {
                hotels: [],
                selectedSort: 'asc',
            },
            methods: {
                getGFG(sort = '', amount = '') {
                    fetch(`/api/get_GFG/?sort_by=/${sort}&amount=/${amount}`)
                        .then(response => response.json())
                        .then(result => this.hotels = result);
                },
                sortBy() {
                    this.getGFG(this.selectedSort);
                },
                priceChange(e) {
                    this.getGFG(' ', e.target.value);
                },
            },
            created() {
                this.getGFG();
            }
        });
    </script>
</body>
</html>
```

---

## 8. Migrations & Superuser

```
python manage.py makemigrations
python manage.py migrate
python manage.py createsuperuser
```

---

## 9. Run Server

```
python manage.py runserver
```
---
