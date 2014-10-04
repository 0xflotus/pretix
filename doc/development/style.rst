Coding style
============

Python code
-----------

* Basically: Follow `PEP 8`_.

  Use `flake8`_ to check for conformance problems. The project includes a setup.cfg
  with a default configuration for flake8 that excludes migrations and other non-relevant
  code parts. It also silences a few checks, ``N802`` (function names should be lowercase) and
  ``E128`` (continuation line under-indented for visual indent) as well as increasing the
  maximum line length to more than 79 characters. **However** you should still name all your
  functions lowercase [#f1]_ and keep your lines short when possible. [#f2]_

* Our build server will reject all code violating other flake8 checks than the following:
  
  * E123: closing bracket does not match indentation of opening bracket’s line
  * E128: continuation line under-indented for visual indent
  * F403: ``from module import *`` used; unable to detect undefined names
  * F401: module imported but unused
  * N802: function names should be lowercase

 So please make sure that you *always* follow all other rules and break these rules *only when
 it makes sense*.

* Indent your code with four spaces.

* For templates and models, follow the `Django Coding Style`_.

* Always mark all strings ever displayed to any user for translation.

LESS stylesheets
----------------

* Indent your code with four spaces.
* Make use of the nesting feature of LESS to put your code in logical groups, but avoid using 
  more then three levels of nesting.
* Put spaces after ``:`` in declarations.
* Put spaces before ``{`` in rulesets.
* When grouping selectors, use one line per selector.
* Place closing brackets on an own line.
* Use only one declaration per line.
* Use the `mixins`_ feature from LESS, especially when dealing with browser-specific statements
  like ``-webkit-transform``, ``-moz-transform``, etc.
* Use hex color codes (or ``rgba()``, if needed)
* Put colors into variables, if you use them more than once (and maybe even then)



.. _PEP 8: http://legacy.python.org/dev/peps/pep-0008/
.. _flake8: https://pypi.python.org/pypi/flake8
.. _Django Coding Style: https://docs.djangoproject.com/en/dev/internals/contributing/writing-code/coding-style/
.. _mixins: http://lesscss.org/features/#mixins-feature
.. [#f1] But Python's very own ``unittest`` module forces us to use ``setUp`` as a method name...
.. [#f2] The underindentation-thing is silenced because PEP8-conforming indentation looks very bad
 in the ``urls.py`` modules.
