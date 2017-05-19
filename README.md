# Django ssl redirect
Django ssl redirect is a middleware for automatically redirecting to HTTPS for specific URLs

## Versions

Tested on Django==1.10.7

## Getting Started

Copy the folder called ##### django_ssl_redirect ##### in the root of the project and now add the
middleware (django_ssl_redirect.middleware.django_ssl_redirect.py) to your MIDDLEWARE's
and comment the django middleware default(django.middleware.security.SecurityMiddleware)
like this:

```python
MIDDLEWARE = [
    'django_ssl_redirect.middleware.django_ssl_redirect.SecurityMiddleware',
    #'django.middleware.security.SecurityMiddleware',
    'django.contrib.sessions.middleware.SessionMiddleware',
    'django.middleware.common.CommonMiddleware',
    'django.middleware.csrf.CsrfViewMiddleware',
    'django.contrib.auth.middleware.AuthenticationMiddleware',
    'django.contrib.messages.middleware.MessageMiddleware',
    'django.middleware.clickjacking.XFrameOptionsMiddleware',
]
```

## Settings Reference

- SECURE_SSL_REDIRECT
If set to True, causes SecurityMiddleware to redirect all non-HTTPS requests to https

- SECURE_REDIRECT_URLS = ['admin']
Is a list of urls that should be secure. Any request to a path which starts with one of these will be required to use https.
In this example try to admin urls.

## Configuration

Set to your (settings.py)

```python
SECURE_SSL_REDIRECT = True
SECURE_REDIRECT_URLS = ['admin']
```
