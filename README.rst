OlaPy, an experimental OLAP engine based on Pandas
==================================================

About
-----

**OlaPy** is an OLAP_ engine with MDX_ support, web interface (slice & dice) and XMLA_ support for Excel clients.

.. _OLAP: https://en.wikipedia.org/wiki/Online_analytical_processing
.. _MDX: https://en.wikipedia.org/wiki/MultiDimensional_eXpressions
.. _XMLA: https://en.wikipedia.org/wiki/XML_for_Analysis

Status
~~~~~~

This project is currently a research prototype, not suited for production use.

Licence
~~~~~~~

This project is currently licenced under the LGPL v3 licence.

Installation
------------

To set up the application, run, ideally in a virtualenv::

    python setup.py install

or just::

    pip install -e .

Usage
-----


To use XMLA from Excel, just start the XMLA server by executing in the root directory::

    python olapy ( -c | --console , if you want to print logs only in the console)

and use the url: http://127.0.0.1:8000/xmla in Excel


Developing
----------

This project must adhere to the `Abilian Developer Guide <http://abilian-developer-guide.readthedocs.io/>`_.

Pull requests are welcome.

Tests
~~~~~

To run tests, run::

    pytest tests

or simply (on Unix-like systems)::

    make test


Credits
-------

This project is developed by `Abilian SAS <https://www.abilian.com>`_ and partially funded by the French Government through the `Wendelin <http://www.wendelin.io/>`_ project and the `Investissement d'avenir <http://www.gouvernement.fr/investissements-d-avenir-cgi>`_ programme.
