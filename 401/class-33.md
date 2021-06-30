# Class 33 Reading Notes

## JSON WEB TOKENS INTRO

### What is JSON Web Token

- open standard that defines a compact and self contained way for securely transmitting info between parties as JSON

### Why Should you use JSON Web Tokens

- Authorization
    -most common scenario

- Information Exchange
    -can send info between parties

### What is a JSON Web Token Structure

- Header
- Payload
- Signature

- looks like the following

xxxxx.yyyyy.zzzzz

### Header

- consists of two parts:
    -type of token
    -signing algorith being used

```py
{
  "alg": "HS256",
  "typ": "JWT"
}
```

### Payload

- contains the claims
- statements about an entity and additional data

#### Registered Claims

- Set of predefined claims which are not mandatory but recommended

#### Public Claims

- defined at will by those using JWT's . Should be defined in the IANA JSON Web Token Registry

#### Private Claims

- custom claims created to share info between parties that agree on using them and are neither registered or public

```py
{
  "sub": "1234567890",
  "name": "John Doe",
  "admin": true
}
```

#### Signature

```py
HMACSHA256(
  base64UrlEncode(header) + "." +
  base64UrlEncode(payload),
  secret)
```

### HOW DO JSON Web Tokens Work?

- the user successfully logs in using their credentials, a JSON web token will be returned

## How to use JWT Authentication with DJango REST Framework

### Installation and Setup

```py
pip install djangorestframework_simplejwt
```

#### Settings.py

```py
REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': [
        'rest_framework_simplejwt.authentication.JWTAuthentication',
    ],
}

```

#### urls.py

```py
from django.urls import path
from rest_framework_simplejwt import views as jwt_views

urlpatterns = [
    # Your URLs...
    path('api/token/', jwt_views.TokenObtainPairView.as_view(), name='token_obtain_pair'),
    path('api/token/refresh/', jwt_views.TokenRefreshView.as_view(), name='token_refresh'),
]
```

#### Views.py Example

```py
from rest_framework.views import APIView
from rest_framework.response import Response
from rest_framework.permissions import IsAuthenticated


class HelloView(APIView):
    permission_classes = (IsAuthenticated,)

    def get(self, request):
        content = {'message': 'Hello, World!'}
        return Response(content)
```

## Django Runserver Is Not Your Production Server

- pmp is NOT THE WAY 

### A Production Stack 

- should be passed to a dedicated web server

- Django actually uses the uwsgi to call a funciton to the application server

- gets a python obj representing the incoming request