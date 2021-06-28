# Class 31 Reading Notes

## Docker

### Intro to Docker

- docker is a way to isolate and run applications regardless of OS

### Linux Containers

- docker is really just a bunch of virtualization

### Containers vs Virtual Environment

- virtual environments still rely on global system level installs (python has to be installed)

- Containers on the other hand, just install things to the environment that anyone can use

### Install Docker

- Download the desktop app

- install

``
sudo pip install docker-compose

docker --version
Docker version 19.03.5, build 633a0ea
``

- to confirm it's working

    -docker run hello-world

### Images and containers

- A Dockerfile is the recipe for a cake
- An image is a snapshot of the recipe at a given time
- A docker-compose.yml says how to make the cake
- And the container is the actual, baked cake

## CH2 Django for API's

- Setup default Django file, duh

### Django REST Framework

- pipenv install djangorestframework~=3.11.0

- the api will list thiungs out in JSON

- a new API app will be created and added in the default apps

### URL's

- api/ for urls is probably best

### api app needs a urls.py

### Views

```py
# api/views.py
from rest_framework import generics

from books.models import Book
from .serializers import BookSerializer


class BookAPIView(generics.ListAPIView):
    queryset = Book.objects.all()
    serializer_class = BookSerializer
```

### Serializers

```py
(library) $ touch api/serializers.py

# api/serializers.py
from rest_framework import serializers

from books.models import Book


class BookSerializer(serializers.ModelSerializer):
    class Meta:
        model = Book
        fields = ('title', 'subtitle', 'author', 'isbn')
```