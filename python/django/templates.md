# django template

## Cargar archivos estáticos (dev)
```html
{% load static %}
<link href="{% static 'core/vendor/bootstrap/css/bootstrap.min.css' %}" rel="stylesheet">
...
<img class="..." src="{% static 'core/img/intro.jpg' %}" alt="">
```
## Url con nombre
```html
<a href="{% url '<url_name>'%}">django url template</a>
```

## formatear fechas
```html
<p>{{ post.published | date: "SHORT_DATE_FORMAT" }}</p>
```

