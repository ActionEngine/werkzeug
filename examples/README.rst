=================
Werkzeug Examples
=================

This directory contains various example applications and example code of
Werkzeug powered applications.

Beside the proof of concept applications and code snippets in the partial
folder they all have external depencencies for template engines or database
adapters (SQLAlchemy only so far). Also, every application has click as
external dependency, used to create the command line interface.


Full Example Applications
=========================

The following example applications are application types you would actually
find in real life :-)


`simplewiki`

    A simple Wiki implementation.

    Requirements:

    -   SQLAlchemy
    -   Creoleparser >= 0.7
    -   genshi

    You can obtain all packages in the Cheeseshop via easy_install.  You have
    to have at least version 0.7 of Creoleparser.

    Usage::

        ./manage-simplewiki.py initdb
        ./manage-simplewiki.py runserver

    Or of course you can just use the application object
    (`simplewiki.SimpleWiki`) and hook that into your favourite WSGI gateway.
    The constructor of the application object takes a single argument which is
    the SQLAlchemy URI for the database.

    The management script for the devserver looks up the an environment var
    called `SIMPLEWIKI_DATABASE_URI` and uses that for the database URI.  If
    no such variable is provided "sqlite:////tmp/simplewiki.db" is assumed.

`plnt`

    A planet called plnt, pronounce plant.

    Requirements:

    -   SQLAlchemy
    -   Jinja2
    -   feedparser

    You can obtain all packages in the Cheeseshop via easy_install.

    Usage::

        ./manage-plnt.py initdb
        ./manage-plnt.py sync
        ./manage-plnt.py runserver

    The WSGI application is called `plnt.Plnt` which, like the simple wiki,
    accepts a database URI as first argument.  The environment variable for
    the database key is called `PLNT_DATABASE_URI` and the default is
    "sqlite:////tmp/plnt.db".

    Per default a few python related blogs are added to the database, you
    can add more in a python shell by playing with the `Blog` model.

`shorty`

    A tinyurl clone for the Werkzeug tutorial.

    Requirements:

    -   SQLAlchemy
    -   Jinja2

    You can obtain all packages in the Cheeseshop via easy_install.

    Usage::

        ./manage-shorty.py initdb
        ./manage-shorty.py runserver

    The WSGI application is called `shorty.application.Shorty` which, like the
    simple wiki, accepts a database URI as first argument.

    The source code of the application is explained in detail in the Werkzeug
    tutorial.

`couchy`

    Like shorty, but implemented using CouchDB.

    Requirements :

    -   werkzeug : http://werkzeug.pocoo.org
    -   jinja : http://jinja.pocoo.org
    -   couchdb 0.72 & above : https://couchdb.apache.org/

`cupoftee`

    A `Teeworlds <https://www.teeworlds.com/>`_ server browser.  This application
    works best in a non forking environment and won't work for CGI.

    Usage::

        ./manage-cupoftee.py runserver
