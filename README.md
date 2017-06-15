#README

Example demonstration of Django Dynamic Forms package

- **Create Virtualenv** with: `virtualenv -p python3 env` or `conda create -n ddf_env python=3` (I use conda!)
- **Activate virtualenv** with: `source activate ddf_env`
- **Install django** with: `pip install django`
- **Install django-dynamic-forms**: `pip install django-dynamic-forms`
- **Start django project**: `django-admin startproject ddf_ex`
- `cd ddf_ex`
- **Edit settings.py**

Add in `INSTALLED_APPS`

```py
INSTALLED_APPS = (
    ...
    'dynamic_forms.apps.DynamicFormsConfig',
    ...
)
```

Add in `MIDDLEWARE_CLASSES`


```py
MIDDLEWARE_CLASSES = (
    ...
    'dynamic_forms.middlewares.FormModelMiddleware'
)
```

Add in `urls.py`

```py
from django.conf.urls import include

urlpatterns = patterns('',
    ...
    url(r'^dynamic_forms/',
        include('dynamic_forms.urls', namespace='dynamic_forms')),
    ...
)
```

- **Apply all migrations**: `python manage.py migrate`
- **Create a superuser**: `python manage.py createsuperuser`
- **Start server**: `python manage.py runserver`
- **Configure dynamic forms with admin**: http://127.0.0.1:8000/admin/

Thats it!

#Recommendation

- The code looks good but constrains ability to make changes to adapt to applications
- Recommend to use code structure but continue to custom code in the main app to create dynamic forms