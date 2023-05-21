---
tag: core-django-concept, python
---
related: [[URL Mapping]], [[Views]]

# load template tag
the load tag takes on on one or more packages/libraries to load into.
- When using the load tag, it must be used after {extends}
- Also note if you have an extend that it itself loads certain packages, you must load those packages everywhere they are needed, extending does not load packages from other templates.
```python
{% load package_one package_two package_three %}
```

# static template tag
first you must load the static template using the load template tag. This is because the static template tag is not a part of the default set of django templates that are automatically loaded.
```python
{% load static %}
```
