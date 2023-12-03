# Admin

## campos de solo lectura
```python
from django.contrib import admin
from .models import Service

# Register your models here.
class ServiceAdmin (admin.ModelAdmin):
  ...
  readonly_fields = ('created', 'updated')

admin.site.register(Service, ServiceAdmin)
```

## mostrar diferentes columna
```py
class PostAdmin (admin.ModelAdmin):
  ...
  list_display = ('title','author','published') # <---

admin.site.register(Post, PostAdmin)
```

## ordenar
```py
class PostAdmin (admin.ModelAdmin):
  ...
  ordering = ('author',) # <--- filtrar 1 vez
  ordering = ('author','published') # <--- filtra primero por 'author' y luego por 'published'
admin.site.register(Post, PostAdmin)
```

