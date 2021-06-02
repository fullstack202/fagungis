===========================================================================
django-fagungis: DJANGO + FAbric + GUnicorn + NGInx + Supervisor deployment
===========================================================================

Introduction
============

django-fagungis allow you to easy setup and deploy your django project on
your linux server.
django-fagungis will install and configure for you:

* nginx

* gunicorn

* supervisor

* virtualenv

Patches are welcome! Feel free to fork and contribute to this project on:

**github**: `github.com/fullstack202/fagungis <https://github.com/fullstack202/fagungis>`_


Installation
============

There are a few different ways to install Fagungis:

Using pip
---------
If you have pip install available on your system, just type::

    pip install django-fagungis

If you've already got an old version of Fagungis, and want to upgrade, use::

    pip install -U django-fagungis

Installing from a directory
---------------------------
If you've obtained a copy of Fagungis using either Mercurial or a downloadable
archive, you'll need to install the copy you have system-wide. Try running::

    python setup.py develop

If that fails, you don't have ``setuptools`` or an equivalent installed;
either install them, or run::

    python setup.py install


How to use fagungis?
====================

If you have already installed Fagungis, you must proceed with the
configuration of your project.

Configuration
-------------

First of all you must configure your project task settings. To do this we
have prepared for you an example file in **path/to/fagungis/example_fabfile.py**
so you can create a copy of this file and modify it according to your
needs.

Please pay attention to not have any tasks in your fabfile.py called:
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""

* setup

* deploy

* test_configuration

* git_pull

or

* hg_pull

because these names are reserved by Fagungis.

Test your configuration first!
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Fagungis come with its own automatic configuration tests. Each time you run
**setup** or **deploy** task, configuration tests are called.
Anyway, you can manually run these tests for your project configuration::

    fab project_name test_configuration

If you run **test_configuration** manually, you'll observe some output about all your project settings.
