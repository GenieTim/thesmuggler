Smuggler 🚬
===========

.. image:: https://travis-ci.org/fny/smuggler.svg?branch=master
   :target: https://travis-ci.org/fny/smuggler
   :alt: Build Status

.. image:: https://badge.fury.io/py/smuggler.svg
   :target: https://pypi.python.org/pypi/smuggler
   :alt: Smuggler on PyPI

Sidestep :code:`import` and load Python files as relative paths.

Intended for one-off imports (e.g. global configuration). Currently, :code:`smuggler` can't import files that import other local packages, but you can :code:`smuggle` files that
have already smuggled other files.

Tested and working on Python 2.7 and up.

Usage
-----

:code:`pip install smuggler`, then:

.. code:: python

    from smuggler import smuggle

    # À la `import weapons`
    weapons = smuggle('weapons.py')

    # À la `from contraband import drugs, alcohol`
    drugs, alcohol = smuggle('drugs', 'alcohol', source='contraband.py')

    # À la `from contraband import drugs as dope, alcohol as booze`
    dope, booze = smuggle('drugs', 'alcohol', source='contraband.py')
