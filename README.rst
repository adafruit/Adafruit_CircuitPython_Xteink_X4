Introduction
============


.. image:: https://readthedocs.org/projects/adafruit-circuitpython-xteink-x4/badge/?version=latest
    :target: https://docs.circuitpython.org/projects/xteink_x4/en/latest/
    :alt: Documentation Status


.. image:: https://raw.githubusercontent.com/adafruit/Adafruit_CircuitPython_Bundle/main/badges/adafruit_discord.svg
    :target: https://adafru.it/discord
    :alt: Discord


.. image:: https://github.com/adafruit/Adafruit_CircuitPython_Xteink_X4/workflows/Build%20CI/badge.svg
    :target: https://github.com/adafruit/Adafruit_CircuitPython_Xteink_X4/actions
    :alt: Build Status


.. image:: https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/astral-sh/ruff/main/assets/badge/v2.json
    :target: https://github.com/astral-sh/ruff
    :alt: Code Style: Ruff

CircuitPython helper library to interface with the Xteink X4 eReader. Based on the [OpenX4 E-Paper Community SDK](https://github.com/open-x4-epaper/community-sdk).


Dependencies
=============
This driver depends on:

* `Adafruit CircuitPython <https://github.com/adafruit/circuitpython>`_

Please ensure all dependencies are available on the CircuitPython filesystem.
This is easily achieved by downloading
`the Adafruit library and driver bundle <https://circuitpython.org/libraries>`_
or individual libraries can be installed using
`circup <https://github.com/adafruit/circup>`_.

Installing from PyPI
=====================

On supported GNU/Linux systems like the Raspberry Pi, you can install the driver locally `from
PyPI <https://pypi.org/project/adafruit-circuitpython-xteink-x4/>`_.
To install for current user:

.. code-block:: shell

    pip3 install adafruit-circuitpython-xteink-x4

To install system-wide (this may be required in some cases):

.. code-block:: shell

    sudo pip3 install adafruit-circuitpython-xteink-x4

To install in a virtual environment in your current project:

.. code-block:: shell

    mkdir project-name && cd project-name
    python3 -m venv .venv
    source .env/bin/activate
    pip3 install adafruit-circuitpython-xteink-x4

Installing to a Connected CircuitPython Device with Circup
==========================================================

Make sure that you have ``circup`` installed in your Python environment.
Install it with the following command if necessary:

.. code-block:: shell

    pip3 install circup

With ``circup`` installed and your CircuitPython device connected use the
following command to install:

.. code-block:: shell

    circup install adafruit_xteink_x4

Or the following command to update an existing version:

.. code-block:: shell

    circup update

Usage Example
=============

.. code-block:: python

	from adafruit_xteink_x4_helper import BatteryMonitor, InputManager

	battery = BatteryMonitor()
	buttons = InputManager()
	
	print(f"Battery: {battery.percentage}% ({battery.volts:.2f}V)")

	while True:
		buttons.update()

		if buttons.any_pressed:
			for i in range(7):
				if buttons.was_pressed(i):
					print(f"Pressed:  {buttons.button_name(i)}")

Documentation
=============
API documentation for this library can be found on `Read the Docs <https://docs.circuitpython.org/projects/xteink_x4/en/latest/>`_.

For information on building library documentation, please check out
`this guide <https://learn.adafruit.com/creating-and-sharing-a-circuitpython-library/sharing-our-docs-on-readthedocs#sphinx-5-1>`_.

Contributing
============

Contributions are welcome! Please read our `Code of Conduct
<https://github.com/adafruit/Adafruit_CircuitPython_Xteink_X4/blob/HEAD/CODE_OF_CONDUCT.md>`_
before contributing to help this project stay welcoming.
