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

# Then you can use the static tag to generate a URL for all your assets
{% static landing/logo.png %}
# renders to
/static/landing/logo.png

# above we have already namespaced our logo.png file. this would be sitting in:
business_site/landing/static/landing/logo.png
```

In a practical setting, we would use the static tag to render in image inside of a normal HTML 
`<img>` tag
```html
<img src="{% static 'landing/logo.png' %}">
<!-- which would render out html like so:-->
<img src="/static/landing/logo.png">
```

Or if we wanted to generate the URL for a linked CSS file
```html
<link href="{% static 'path/to/file.css' %}" rel="stylesheet">
<!-- which would render out html like so:-->
<link href="/static/path/to/file.css" rel="stylesheet">
```

## the as suffix

you can use the `as[attribute]` to assign the result to a variable, which you can use again elsewhere. This can be useful if you have an image that you want to use in multiple places. 