===============================================
django-i18next
===============================================
`django-i18next` - Additions to Django's i18n module.

Prerequisites
===============================================
- Django 1.4, 1.5, 1.6, 1.7, 1.8
- Python >= 2.6.8, >= 2.7, >= 3.3

Roadmap
===============================================
See the `TODOS <https://raw.githubusercontent.com/barseghyanartur/django-i18next/master/TODOS.rst>`_
for the full list of planned-, pending- in-development- or to-be-implemented
features.

Installation
===============================================

(1) Install latest stable version from PyPI:

.. code-block:: none

    $ pip install django-i18next

Or latest stable version from GitHub:

.. code-block:: none

    $ pip install -e git+https://github.com/barseghyanartur/django-i18next@stable#egg=django-i18next

Or latest stable version from BitBucket:

.. code-block:: none

    $ pip install -e hg+https://bitbucket.org/barseghyanartur/django-i18next@stable#egg=django-i18next

(2) Add `fobi` to ``INSTALLED_APPS`` of the your projects' Django settings.
    Furthermore, all themes and plugins to be used, shall be added to the
    ``INSTALLED_APPS`` as well. Note, that if a plugin has additional
    dependencies, you should be mentioning those in the ``INSTALLED_APPS``
    as well.

.. code-block:: python

    INSTALLED_APPS = (
        # ...
        'i18next',

        # Other project specific apps
        'foo', # Test app
        # ...
    )

Usage
===============================================
Override locale
-----------------------------------------------
No matter what your current locale is, you can override it for a certain part
of your template using the ``overridelocale`` template tag.

.. code-block:: html

    {% load i18n i18next %}

    {% overridelocale 'en' %}
        <p>
            <a href="/login/">{% trans "Log in" %}</a>
        </p>
    {% endoverridelocale %}

Disable translations
-----------------------------------------------
No matter what your current locale is, you can disable translations for a
certain part of your template using the ``disabletranslations`` template tag.

.. code-block:: html

    {% load i18n i18next %}

    {% disabletranslations %}
        <p>
            <a href="/login/">{% trans "Log in" %}</a>
        </p>
    {% enddisabletranslations %}

Demo
===============================================
Live demo
-----------------------------------------------
See the `live demo app <https://django-i18next.herokuapp.com/>`_ on Heroku.

Credentials:

- username: test_user
- password: test_user

Run demo locally
-----------------------------------------------
In order to be able to quickly evaluate the `Fobi`, a demo app (with a quick
installer) has been created (works on Ubuntu/Debian, may work on other Linux
systems as well, although not guaranteed). Follow the instructions below for
having the demo running within a minute.

Grab the latest `django_fobi_example_app_installer.sh`:

.. code-block:: none

    $ wget https://raw.github.com/barseghyanartur/django-i18next/stable/examples/django_i18next_example_app_installer.sh

Assign execute rights to the installer and run the
`django_i18next_example_app_installer.sh`:

.. code-block:: none

    $ chmod +x django_i18next_example_app_installer.sh
    $ ./django_i18next_example_app_installer.sh

Open your browser and test the app.

Dashboard:

- URL: http://127.0.0.1:8001/fobi/
- Admin username: test_admin
- Admin password: test

Django admin interface:

- URL: http://127.0.0.1:8001/admin/
- Admin username: test_admin
- Admin password: test

If quick installer doesn't work for you, see the manual steps on running the
`example project
<https://github.com/barseghyanartur/django-i18next/tree/stable/examples>`_.

Debugging
===============================================
By default debugging is turned off. Set the ``I18NEXT_DEBUG`` to True
in the ``settings.py`` of your project in order to do so.

License
===============================================
GPL 2.0/LGPL 2.1

Support
===============================================
For any issues contact me at the e-mail given in the `Author` section.

Author
===============================================
Artur Barseghyan <artur.barseghyan@gmail.com>

Documentation
===============================================
Contents:

.. toctree::
   :maxdepth: 20

   fobi
   quickstart

Indices and tables
===============================================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
