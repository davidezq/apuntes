# Django cheatsheet

## version
```shell
python -m django --version
```

## Iniciar un proyecto
```shell
django-admin startproject <nombre_proyecto>
```

## Iniciar el servidor de desarrollo
```shell
python manage.py runserver
python manage.py runserver 8080
python manage.py runserver 0.0.0.0:8080
```

## Crear una app
```shell
python manage.py startapp <nombre_app>
```

## Hacer una migracion/migraciones
```shell
python manage.py makemigrations
```

## Ejecutar las migraciones
```shell
python manage.py migrate
```
