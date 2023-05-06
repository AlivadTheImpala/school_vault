#core-django-concept #python 
the code in this note is in refere
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

# Forms in admin app
When taking a closer look at the forms generated in an admin app lets use the reviews app as an example. When creating a model in django, we add certain attributes to our variables, like CharField, URLField, and EmailField. This results in Django creating the coresponding HTML attributes for the form created using this model.
```python
class Publisher(models.Model):
"""A company that publishes books."""
    
    name = models.CharField(max_length=50,
	    help_text="The name of the Publisher.")

    website = models.URLField(help_text="The Publisher's website.")

    email = models.EmailField(help_text="The Publisher's email address.")
```

The following is the corresponding HTML generated based on the Publisher Model above
```html
<input type="text" 
	   name="name" 
	   value="Packt Publishing"
	   class="vTextField" 
	   maxlength="50"
	   required=""
	   id="id_name">
	   
<input type="url" 
	   name="website" 
	   value="https://www.packtpub.com/"
	   class="vURLField" 
	   maxlength="200" 
	   required=""
	   id="id_website">            

<input type="email" 
	   name="email" 
	   value="info@packtpub.com"
	   class="vTextField" 
	   maxlength="254" 
	   required=""
	   id="id_email">
```

## Forms rendered in the admin app.
![[Screenshot 2023-05-06 at 15.15.08.png]]