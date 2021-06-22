# Class 27 Reading Notes

## Using Models

### Model primer

#### Model definition

- subclass of django.db.models.Model 

#### Fields

- a model can have an arbitrary number of fields, of any type, each represents a column of data that we want to store

```py
my_field_name = models.CharField(max_length=20, help_text='Enter field documentation')
```

- this field will contain strings of alphanumeric characters. 

- Fields can take arguments

- above max len is 20

- "help_text='Enger field documentation"
    -provides a text label to disiplay to help users known what value to provide when this value is to be entered

#### Common field arguments

- help_text
- verbose_name
- default
- null
- blank
- choices
- primary_key

#### Common field types

- CharField
- TextField
- IntergerField
- DateField
- EmailField
- FileField
- AutoField
- ForeignKey
- ManyToManyField

#### Metadata

- you can declare model-leel metadata with 

```py
class Meta:
    ordering = ['-my_field_name']

```

#### Methods

- models can also have methods

- define EVERY model with

```py
def __str__
 ```

## Django Admin Site

### Registering Models

- admin.py

```py
from django.contrib import admin

# Register your models here.

from .models import Author, Genre, Book, BookInstance

admin.site.register(Book)
admin.site.register(Author)
admin.site.register(Genre)
admin.site.register(BookInstance)

```

### Creating a superuser

- python3 manage.py createsuperuser
- python3 manage.py runserver

### Logging in and using the site

- http://127.0.0.1:8000/admin

### Confugure list views

```py
class AuthorAdmin(admin.ModelAdmin):
    list_display = ('last_name', 'first_name', 'date_of_birth', 'date_of_death')
```

### Add List Filters

- list_filter attribute

```py
class BookInstanceAdmin(admin.ModelAdmin):
    list_filter = ('status', 'due_back')

```

### Organize detail view layout

- by default, the detail views out all fields verticallly

