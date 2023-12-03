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
