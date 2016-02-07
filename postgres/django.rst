
Django database settings::

    DATABASES = {
        'default': {
             'ENGINE': 'django.db.backends.postgresql',
             'NAME': 'myapp',
             'USER': 'myapp',
             'PASSWORD': ...
             'HOST': ...
             'PORT': ...
        },
    }

The django test runner creates and deletes a new database for every test run, so the
'myapp' role needs the CREATEDB privilege in order to run tests::

    CREATE ROLE "myapp" LOGIN PASSWORD 'mysecret' INHERIT CREATEDB;

Or, to update an existing role::

    ALTER ROLE "myapp" CREATEDB;

Create the database::

    CREATE DATABASE "myapp" WITH OWNER "myapp" ENCODING 'utf8';

