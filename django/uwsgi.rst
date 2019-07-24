==============
uWSGI Install
==============

install into venv::

    pip install uwsgi

Testing with test.py::

    def application(env, start_response):
        start_response('200 OK', [('Content-Type','text/html')])
        return [b"Hello World"]

Run it with uWSGI::

    uwsgi --http :8000 --wsgi-file test.py

Get 'Hello World' from http://example.com:8000

These Clients work together::

    the web client <-> uWSGI <-> Python

Run Django with uWSGI::

    uwsgi --http :8000 --module mysite.wsgi

Get Django-Startpage from http://example.com:8000
