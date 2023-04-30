#python
Back to [[Web Development]]
***
- [[PIP]]
- [[Django Commands]]
- [[PyCharm]]
- [[URL Mapping]]
- [[Views]]
- [[Templates]]
- [[Models]]
- [[Django]]
## Useful methods 
**get():** this method can be used to fetch the value of one object and its values. Here we are fetching the website. The output is displayed in the shell due to adding the model method ``__str__()`` in the publisher class.
```python
>>>from reviews.models import Publisher
>>> publisher = Publisher.objects.get(name='Pocket Books')
>>> publisher
>>> <Publisher: Pocket Books> # output displayed in the shell

# you can fetch any attribute of the object using . after class name
>>>publisher.website
'https://pocketbookssampleurl.com'
```

**all():** if you want to access all of the objects use all() to return a QuerySet 
```python
>>>from reviews.models import Contributor
>>>Contributor.objects.all()
<QuerySet [<Contributor: Rowel>, <Contributor: Packt>, <Contributor: Packtp>, <Contributor: Stephen>, <Contributor: Peter>]>

# you can list the objects in order to look up specific values 
```