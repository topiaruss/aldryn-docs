.. _addon-packaging:

Packaging and Sourcecode
========================

If you want to write an addon, write a standard Django app (including working setup.py!).

An addon requires a configuration file named ``addon.json`` which follows the general json guidelines.
Place this file next to your setup.py and you should be ready to run ``aldryn addon validate``.

All addons **must** have a valid license file. Preferably called ``LICENSE.txt`` in the root
of the Project.

The following is an example of a configuration file using all options:

.. code-block:: json

    {
        "name": "My Addon",
        "description": "This is my custom application.",
        "url": "https://github.com/aldryn",
        "package-name": "my-addon",
        "installed-apps": [
            "my_addon"
        ],
        "author": {
            "name": "Divio",
            "url": "https://www.aldryn.com"
        },
        "license": {
            "name": "BSD"
        }
    }

.. NOTE:: Please follow a strict :ref:`Versioning Scheme <versioning>`!


Options
-------

.. option:: name

   The name of your Boilerplate

.. option:: description

   A description of your Boilerplate

.. option:: version

   The version of this Boilerplate (must be compatible with LooseVersion)

.. option:: url

   The url to your repository or website

.. option:: package—name

   The **package** name of your app (the thing you have in the setup.py under ``name``)

.. option:: installed—apps

   A list of apps that needs to be added to the ``INSTALLED_APPS`` to make your app work.

.. option:: author

   .. option:: name:

      Your name!

   .. option:: url:

      URL to your website (optional)

.. option:: license

   .. option:: name:

      Type of the license, e.g. BSD, MIT


Source Repository Guidelines
----------------------------

Use our cookie-cutter template for addons: https://github.com/divio/cookiecutter-aldryn-addon

The Source should contain:

``README.rst``
~~~~~~~~~~~~~~

A short introduction what the package is about. Installation instructions (non-aldryn, like with any other package)

.. TODO:: more guidelines. link to someplace where this is well described.

Include a link back to aldryn

* rst: ``This package is compatible with `Aldryn <http://www.aldryn.com>`_.``
* markdown: ``This package is compatible with [Aldryn](http://www.aldryn.com).``

``LICENSE.txt``
~~~~~~~~~~~~~~~

.. TODO:: links/description of common licenses

http://en.wikipedia.org/wiki/List_of_software_licenses


``MANIFEST.in``
~~~~~~~~~~~~~~~

::

    include LICENSE.txt
    include README.rst
    recursive-include mypackage/templates *
    recursive-include mypackage/static *
    recursive-include mypackage/locale *
    recursive-exclude * *.pyc

