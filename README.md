# Design a Website for Server Side Processing

## AIM:
To design a website to perform mathematical calculations in server side.

## DESIGN STEPS:

### Step 1:

clone the repository from github

### Step 2:

create django admin project.

### Step 3:

create a new app

### Step 4:

create a python programs for views and url

### Step 5:

create a HTML file of forms.

### Step 6:

Publish the website in the given URL.

## PROGRAM :```math.html
<html>
<head>
<meta charset='utf-8'>
<meta http-equiv='X-UA-Compatible' content='IE=edge'>
<title>Area of prism</title>
<meta name='viewport' content='width=device-width, initialscale=1'>
<style type="text/css">
body
{
background-color:cyan;
}
.edge {
width: 1080px;
margin-left: auto;
margin-right: auto;
padding-top: 200px;
padding-left: 300px;
}
.box {
display:block;
5 of 8 22/11/23, 21:17
display:block;
border: Thick dashed lime;
width: 500px;
min-height: 300px;
font-size: 20px;
background-color: purple;
}
.formelt{
color: Red;
text-align: center;
margin-top: 5px;
margin-bottom: 5px;
}
h1
{
color: yellow;
text-align: center;
padding-top: 20px;
}
</style>
</head>
<body>
<div class="edge">
<div class="box">
<h1>Area of a prism</h1>
<form method="POST">
{% csrf_token %}
<div class="formelt">
side : <input type="text" name="side" value="{{s}}"></input>(in
m)<br/>
</div>
<div class="formelt">
height : <input type="text" name="height" value="{{h}}">
</input>(in m)<br/>
</div>
<div class="formelt">
<input type="submit" value="Calculate"></input><br/>
</div>
<div class="formelt">
Area : <input type="text" name="area" value="{{area}}">
</input>m<sup>2</sup><br/>
</div>
</form>
</div>
</div>
</body>
</html>
views.py
from django.shortcuts import render
from django.template import loader
# Create your views here.
def prismarea(request):
 context={}
 context['side'] = "0"
 context['s'] = "0"
 context['h'] = "0"
 if request.method == 'POST':
 print("POST method is used")
 s = request.POST.get('side','0')
 h = request.POST.get('height','0')
 print('request=',request)
 print('side=',s)
 print('height=',h)
 area =2*int(s) * int(s)+4*int(s)*int(h)
 context['area'] = area
 context['s'] = s
 context['h'] = h
 print('Area=',area)
 return render(request,'myapp/math.html',context)
 urls.py
 """myproj URL Configuration
The `urlpatterns` list routes URLs to views. For more 
```
## OUTPUT:
![image](https://github.com/vijayashreeb/serversideprocessing/assets/147474814/a6a40027-c963-4212-a168-a343045d75e2)

### Home Page:
![image](https://github.com/vijayashreeb/serversideprocessing/assets/147474814/559d96bb-0fc9-47f4-ab97-540afd5081bb)


## Result:
The program for server side processing is completed successfully.
