# django template

## Cargar archivos estáticos (dev)
```html
{% load static %}
<link href="{% static 'core/vendor/bootstrap/css/bootstrap.min.css' %}" rel="stylesheet">
...
<img class="..." src="{% static 'core/img/intro.jpg' %}" alt="">
```
##
