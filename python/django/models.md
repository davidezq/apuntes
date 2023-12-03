# modelos

## relación de uno a muchos
```py
class Post(models.Model):
  ...
  author = models.ForeignKey(User, verbose_name = "autor", on_delete=models.CASCADE)
```

## relación de muchos a muchos
```py
class Post(models.Model):
  ...
  # related_name -> cambia el nombre de la relación en la tabla 'hija'
  categories = models.ManytoManyField(Category, verbose_name="Categorias", related_name="get_posts")
```

## obtener todos los objetos de un modelo de la base de datos
```py
Model.objects.all
```

## obtener un único objeto
```py
Model.objects.get(id=)
```

## obtener objetos por filtro
```py
# obtiene el objecto que contenga el valor del otro objeto
Model.objects.filter(<propiedad>=objeto_de_relacion)
```
## obtener los objetos de una relación de manera inversa
```py
Model.post_set.all # buscar
```



