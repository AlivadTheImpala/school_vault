#core-django-concept #python 

___
# Admin App
the admin app allows us an easy to use [[CRUD]] system to modify and create information. with admin.site.register() you can create a forms basic schema with the models created for our database in models.py
```python
admin.site.register('class model name goes here')

# example of admin.py
from django.contrib import admin  
from reviews.models import Publisher, Contributor, Book, BookContributor, Review  
  
# Register your models here so that they can be displayed in the admin app  
admin.site.register(Publisher)  
admin.site.register(Contributor)  
admin.site.register(Book)  
admin.site.register(BookContributor)  
admin.site.register(Review)
```