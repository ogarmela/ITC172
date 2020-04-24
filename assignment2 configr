 6  TechReviewProj/TechReviewApp/urls.py 



@@ -0,0 +1,6 @@



from django.urls import path





urlpatterns=[





]



  BIN +95 Bytes (100%) TechReviewProj/TechReviewProj/__pycache__/settings.cpython-36.pyc 



Binary file not shown.



  BIN +930 Bytes TechReviewProj/TechReviewProj/__pycache__/urls.cpython-36.pyc 



Binary file not shown.



  9  TechReviewProj/TechReviewProj/settings.py 



@@ -37,6 +37,7 @@



    'django.contrib.sessions',



    'django.contrib.messages',



    'django.contrib.staticfiles',



    'TechReviewApp',



]



MIDDLEWARE = [



@@ -75,8 +76,12 @@







DATABASES = {



    'default': {



        'ENGINE': 'django.db.backends.sqlite3',



        'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),



        'ENGINE': 'django.db.backends.postgresql_psycopg2',



        'NAME': 'techreviewdb',



        'USER' : 'postgres',



        'PASSWORD': 'P@ssw0rd1',



        'HOST' :'localhost',



        'PORT' :'',



    }



}



  3  TechReviewProj/TechReviewProj/urls.py



@@ -14,8 +14,9 @@



    2. Add a URL to urlpatterns:  path('blog/', include('blog.urls'))



"""



from django.contrib import admin



from django.urls import path



from django.urls import path, include



urlpatterns = [



    path('admin/', admin.site.urls),



    path('TechReviewApp/', include('TechReviewApp.urls')),



]
