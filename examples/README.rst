====================================
Example project for `django-i18next`
====================================
Follow instructions below to install the example project. Commands below are
written for Ubuntu/Debian, but may work on other Linux distributions as well.

- Create a new- or switch to existing- virtual environement.

.. code-block:: sh

    virtualenv i18next

    source i18next/bin/activate

- Download the latest stable version of django-i18next.

.. code-block:: sh

    wget https://github.com/barseghyanartur/django-i18next/archive/stable.tar.gz

- Unpack it somewhere.

.. code-block:: sh

    tar -xvf stable.tar.gz

- Go to the unpacked directory.

.. code-block:: sh

    cd django-i18next-stable

- Install Django, requirements and finally django-i18next.

.. code-block:: sh

    pip install Django

    pip install -r example/requirements.txt

    pip install -e git+https://github.com/barseghyanartur/django-i18next@stable#egg=django-i18next

- Create some directories.

.. code-block:: sh

    mkdir -p examples/media/static/ examples/static/ examples/db/ examples/logs

- Copy local_settings.example

.. code-block:: sh

    cp examples/simple/local_settings.example examples/simple/local_settings.py

- Run the commands to sync database, install test data and run the server.

.. code-block:: sh

    python examples/example/manage.py syncdb --noinput --traceback -v 3

    python examples/example/manage.py migrate --noinput

    python examples/example/manage.py collectstatic --noinput --traceback -v 3

    python examples/example/manage.py i18next_create_test_data --traceback -v 3

    python example/example/manage.py runserver 0.0.0.0:8001 --traceback -v 3

- Open your browser and test the app.
