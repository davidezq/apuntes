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
from django.shortcuts import get_object_or_404
from django.http import HttpResponse,render

def index(request):
    return HttpResponse("Hello, world. You're at the polls index.")

# renderizar una plantilla
def index(request):
    return render(request, "core/index.html")

# renderizar pasando un 'path variable'
# en urls.py
# path('/category/<int:category_id>/', views.category, name='category')
def category(request,category_id):
    # category = Category.objects.get(id=category_id)
    category = get_object_or_404(Category,id=category_id)
    return render(request, "blog/category.html", {'category': category})
```
