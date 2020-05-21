BIN +123 Bytes (140%) TechReviewProject/TechReviewApp/__pycache__/urls.cpython-36.pyc 

Binary file not shown.

  BIN +554 Bytes (190%) TechReviewProject/TechReviewApp/__pycache__/views.cpython-36.pyc 

Binary file not shown.

  18  TechReviewProject/TechReviewApp/templates/TechReviewApp/productdetail.html 

@@ -0,0 +1,18 @@

{% extends 'base.html' %}

{% block content %}

<h2>{{ prod.productname }}</h2>

<p>{{ prod.techtype }}</p>

<p>{{ prod.productURL }}</p>

<p>{{ prod.productprice }}</p>

<p>{{ prod.user }}</p>

<p>{{ prod.productdescription }}</p>

<p>Number of Reviews: {{ reviewcount }}</p>

<h3>Reviews</h3>

{% for r in reviews %}

  <h4>{{ r.reviewtitle }}</h4>

  <p>{{ r.reviewdate }}</p>

  <p>{{ r.reviewrating }}</p>

  <p> {{ r.reviewtext }}</p>

{% endfor %}



{% endblock %} 

  17  TechReviewProject/TechReviewApp/templates/TechReviewApp/products.html 

@@ -0,0 +1,17 @@

{% extends 'base.html' %}

{% block content %}

<h2>Products</h2>

<table class="table">

    <tr>

        <th>Product Name</th>

        <th>Product Type</th>

    </tr>

    {% for p in product_list %}

        <tr>

            <td><a href="{% url 'productdetail' id=p.id %}">{{ p.productname }}</a></td>

            <td>{{ p.techtype }}</td>

        </tr>

    {% endfor %}

</table>



{% endblock %} 

  2  TechReviewProject/TechReviewApp/templates/base.html 

@@ -17,7 +17,7 @@ <h1>Tech Reviews</h1>

</div> 

<ul class="nav navbar-nav"> 

<li><a href="{% url 'types' %}">Types</a></li>

<li>Dummy</li> 

<li><a href="{% url 'products' %}">Products</a></li> 

</ul> 

</div> 

</nav> 

  4  TechReviewProject/TechReviewApp/urls.py 

@@ -4,6 +4,8 @@

#this is a comment

urlpatterns=[

    path('', views.index, name='index'),

    path('getTypes/', views.getTypes, name='types')

    path('getTypes/', views.getTypes, name='types'),

    path('getProducts/', views.getProducts, name='products'),

    path('productDetail/<int:id>',views.productDetail, name='productdetail'),

]
  19  TechReviewProject/TechReviewApp/views.py 

@@ -1,4 +1,4 @@

from django.shortcuts import render

from django.shortcuts import render, get_object_or_404

from .models import TechType, Product, Review

# Create your views here.

@@ -8,4 +8,19 @@ def index(request):

def getTypes(request):

    types_list=TechType.objects.all()

    context={'types_list' : types_list }

    return render(request, 'TechReviewApp/types.html', context=context) 

    return render(request, 'TechReviewApp/types.html', context=context)

def getProducts(request):

    product_list=Product.objects.all()

    return render(request, 'TechReviewApp/products.html',{'product_list' : product_list})

def productDetail(request, id):

    prod=get_object_or_404(Product, pk=id)

    reviewcount=Review.objects.filter(product=id).count()

    reviews=Review.objects.filter(product=id)

    context={

         'prod' : prod,

         'reviewcount' : reviewcount,

         'reviews': reviews,

    }

    return render (request, 'TechReviewApp/productdetail.html', context=context) 
