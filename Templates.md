---
tag: core-django-concept, python
---
related: [[URL Mapping]], [[Views]]

# load template tag
the load tag takes on on one or more packages/libraries to load into 
```python
{% load package_one package_two package_three %}
```

# static template tag
first you must load the static template using the load template tag. This is because the static template tag is not a part of the default set of django templates that are automatically loaded.
```python
{% load static %}
```
