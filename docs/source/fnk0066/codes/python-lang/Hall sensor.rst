################################################################
Chapter Hall sensor 
################################################################

.. include:: ../common/com.Hall sensor_1.rst

Code
================================================================

Python Code 29.1.1 HallSensor
----------------------------------------------------------------

First observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:`  support@freenove.com

1.  Use ``cd`` command to enter 29.1.1_HallSensor directory of Python code.

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/Python_GPIOZero_Code/29.1.1_HallSensor

2.  Use python command to execute code ``HallSensor.py``

.. code-block:: console

    $ python  HallSensor.py

After the program is executed, when the sensor is close to the magnetic field (horn) by hand, the LED will turn on, and if the sensor does not sense the magnetic field (horn), the LED will turn off.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/29.1.1_HallSensor/HallSensor.py
    :linenos: 
    :language: python

Import the HallSensor class from the sensor module. HallSensor is similar to the MotionSensor class in the GPIO Zero library in that they both actually use the SmoothedInputDevice class.

.. code-block:: python

    from sensor import HallSensor

.. seealso::

    For more information about the methods used by the SmoothedInputDevice class in the GPIO Zero library,please refer to: https://gpiozero.readthedocs.io/en/stable/api_input.html#smoothedinputdevice

.. include:: ../common/com.Hall sensor_2.rst

Code
================================================================

Python Code 29.2.1 Alertor
----------------------------------------------------------------

First observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:`  support@freenove.com

1.  Use ``cd`` command to enter 29.2.1_Alertor directory of Python code

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/Python_GPIOZero_Code/29.2.1_Alertor

2.  Use python command to execute code ``Alertor.py``

.. code-block:: console

    $ python Alertor.py

After the program is executed, every time the sensor is close to the magnetic field (speaker) by hand, the buzzer will sound an alarm, and the LED will flash to remind.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/29.2.1_Alertor/Alertor.py
    :linenos: 
    :language: python


