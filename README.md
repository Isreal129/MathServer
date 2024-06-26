# Ex.05 Design a Website for Server Side Processing
## Date:

## AIM:
To design a website to find surface area of a Right Cylinder in server side.

## FORMULA:
Surface Area = 2Πrh + 2Πr<sup>2</sup>
<br>r --> Radius of Right Cylinder
<br>h --> Height of Right Cylinder

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App under the Django Admin project.

### Step 4:
Create python programs for views and urls to perform server side processing.

### Step 5:
Create a HTML file to implement form based input and output.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
## views.py
```
from django.shortcuts import render
def surfacearea(request):
    context = {}
    context['area'] = "0"
    context['r'] = "0"
    context['h'] = "0"
    
    if request.method == 'POST':
        print("POST method is used")
        
        print('request.POST:', request.POST)
        
        r = request.POST.get('radius', '0') 
        h = request.POST.get('height', '0') 
        print('radius =', r)
        print('height =', h)
        
        area = 2 * 3.14 * int(r) * int(h) + 2*3.14*int(r)*int(r)
        context['area'] = area
        context['r'] = r
        context['h'] = h
        print('Area =', area)
    
    return render(request, 'app1/index.html', context)
```
## urls.py
```
from django.contrib import admin
from django.urls import path
from app1 import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('areaofsurface/',views.surfacearea,name="areaofsurface"),
    path('',views.surfacearea,name="areaofsurfaceroot")
]
```
## SERVER SIDE PROCESSING:
![image](https://github.com/Isreal129/MathServer/assets/125784931/dae6c42c-14c3-4530-94e4-55e8b83c78e0)



## HOMEPAGE:
![image](https://github.com/Isreal129/MathServer/assets/125784931/66a0b03c-5364-4680-bd8a-951cdf785ad7)
![image](https://github.com/Isreal129/MathServer/assets/125784931/7c5a1823-e499-4d49-aa59-5270afd4c101)

## RESULT:
The program for performing server side processing is completed successfully.
