# Class 32 Reading Notes

## Django Rest Framework Permissions

### Permissions

- permission checks are run at the start of the view

- request.user request.auth

- a user gets the class **IsAuthenticated** if they're authenticated

### How permissions are determined

- always defined as a list of permission classes

### Object Level Permissons

```py
def get_object(self):
    obj = get_object_or_404(self.get_queryset(), pk=self.kwargs["pk"])
    self.check_object_permissions(self.request, obj)
    return obj

```

### Setting the permission policy 

```py
REST_FRAMEWORK = {
    'DEFAULT_PERMISSION_CLASSES': [
        'rest_framework.permissions.IsAuthenticated',
    ]
}
```

- if not specified, the permissions will say **permissions.AllowAny**

