# modelos

# relación de uno a muchos
```py
class Post(models.Model):
  ...
  author = models.ForeignKey(User, verbose_name = "autor", on_delete=models.CASCADE)
```
# relación de muchos a muchos
```py
class Post(models.Model):
  ...
  categories = models.ManytoManyField(Category, verbose_name="Categorias")
```

## obtener todos los objetos de un modelo de la base de datos
```py
Model.objects.all
```

## obtener un único objeto
```py
Model.objects.get(id=)
```




