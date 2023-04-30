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
get(): this method can be used to fetch the value of one object and its values. Here we are fetching the website. The output is displayed in the shell due to adding the model method ``__str__()`` in the publisher class.
```python
>>> publisher = Publisher.objects.get(website='https://pocketbookssampleurl.com')
'https://pocketbookssampleurl.com'
# after retrieving the object you can also  
>>>publisher.name
'Pocket Books'
```
all(): 