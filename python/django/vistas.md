# vistas

## Directorio para usar plantillas
```
mysite/
    manage.py
    mysite/ <-- proyect
    core/ <-- app
        static/
            index.html
            about.html
        templates/
            index.html
            about.html
```

## Crear una vista
```python
from django.http import HttpResponse,render

def index(request):
    return HttpResponse("Hello, world. You're at the polls index.")

# renderizar una plantilla
def index(request):
    return render(request, "core/index.html")
```
