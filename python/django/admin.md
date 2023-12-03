# Admin

## campos de solo lectura
```python
from django.contrib import admin
from .models import Service

# Register your models here.
class ServiceAdmin (admin.ModelAdmin):
  ...
  readonly_fields = ('created', 'updated')
  ...

admin.site.register(Service, ServiceAdmin)
```

## mostrar diferentes columna
```py
class PostAdmin (admin.ModelAdmin):
  ...
  list_display = ('title','author','published') # <---
  ...

admin.site.register(Post, PostAdmin)
```

## ordenar
```py
class PostAdmin (admin.ModelAdmin):
  ...
  ordering = ('author',) # <--- filtrar 1 vez
  ordering = ('author','published') # <--- filtra primero por 'author' y luego por 'published'
  ...

admin.site.register(Post, PostAdmin)
```

## Crear un buscador
```py
class PostAdmin (admin.ModelAdmin):
  ...
  search_fields = ('title') # <--- permite buscar por un único campo
  search_fields = ('title', 'content') # <--- permite buscar por varios campos
  search_fields = ('title', 'content', 'author__username') # <--- para las relaciones se indica el campo__campo-tabla-externa
  ...

admin.site.register(Post, PostAdmin)
```

## filtrar por fechas
```py
class PostAdmin (admin.ModelAdmin):
  ...
  date_hierarchy = 'published' # <--- debe ser de tipo date
  ...

admin.site.register(Post, PostAdmin)
```

## generar filtros

```py
class PostAdmin (admin.ModelAdmin):
  ...
  list_filter = ('author__username',) # <--- se recomiendan que sean campos de relaciones
  list_filter = ('author__username','categories__name')
  ...

admin.site.register(Post, PostAdmin)
```

## creando nuestras propias columnas
```py
class PostAdmin (admin.ModelAdmin):
  ...
  list_display = ('title','author','published', 'post_categories') # <---

  def post_categories(self,obj):
    return ", ".join([c.name for c in obj.categories.all().order_by('name')])
  ...

admin.site.register(Post, PostAdmin)
```

```py
# cambiando el nombre de la columna
class PostAdmin (admin.ModelAdmin):
  ...
  list_display = ('title','author','published', 'post_categories') # <---

  def post_categories(self,obj):
    return ", ".join([c.name for c in obj.categories.all().order_by('name')])

  post_categories.short_description = 'categorias'
  ...

admin.site.register(Post, PostAdmin)
```
