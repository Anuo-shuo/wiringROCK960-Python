Note
~~~~

wiringROCK960 for Python
===================

wiringROCK960: An implementation of most of the Arduino Wiring functions for
the Orange Pi and ROCK960.

Supported boards
===================
tested on:
``Orange Pi Zero2``
``Orange Pi 3 LTS``
``Orange Pi 4 LTS``
``ROCK960``

Manual Build
============

Get/setup repo
--------------

.. code:: bash

    git clone --recursive https://github.com/Anuo-shuo/wiringROCK960-Python
    git clone --recursive https://ghproxy.com/https://github.com/Anuo-shuo/wiringROCK960-Python
    cd wiringROCK960-Python

Don't forget the --recursive; it is required to also pull in the WiringROCK960 C code from its own repository.

Prerequisites
-------------

To rebuild the bindings you **must** first have installed ``swig``,
``python3-dev``, and ``python3-setuptools``. wiringOP should also be installed system-wide for access
to the ``gpio`` tool.

.. code:: bash

    sudo apt-get install swig python3-dev python3-setuptools

Build & install with
--------------------

``python3 generate-bindings.py > bindings.i``

``sudo python3 setup.py install``

Usage
=====
``sudo python3``
    
.. code:: python

    import wiringpi

    # One of the following MUST be called before using IO functions:
    wiringpi.wiringPiSetup()      # For sequential pin numbering

**General IO:**

.. code:: python

    wiringpi.pinMode(6, 1)       # Set pin 6 to 1 ( OUTPUT )
    wiringpi.digitalWrite(6, 1)  # Write 1 ( HIGH ) to pin 6
    wiringpi.digitalRead(6)      # Read pin 6
