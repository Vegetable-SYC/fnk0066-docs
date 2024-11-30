################################################################
Chapter Infrared Obstacle Avoidance Sensor
################################################################

.. include:: ../common/com.Infrared Obstacle Avoidance Sensor_1.rst

Code
================================================================

Python Code 30.1.1 InfraredSensor
----------------------------------------------------------------

First observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:`  support@freenove.com

1.  Use ``cd`` command to enter 30.1.1_InfraredSensor directory of Python code.

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/Python_GPIOZero_Code/30.1.1_InfraredSensor

2.  Use python command to execute code ``InfraredSensor.py``

.. code-block:: console

    $ python InfraredSensor.py

After the program is executed, when you block the sensor with your hand at a certain distance or the sensor encounters an obstacle, the LED will turn on, and when the sensor is not blocked or the sensor does not encounter an obstacle, the LED will turn off.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/30.1.1_InfraredSensor/InfraredSensor.py
    :linenos: 
    :language: python

Import the InfraredSensor class from the sensor module. InfraredSensor is similar to the MotionSensor class in the GPIO Zero library in that they both actually use the SmoothedInputDevice class.

.. code-block:: python

    from sensor import InfraredSensor

.. seealso::

    For more information about the methods used by the SmoothedInputDevice class in the GPIO Zero library,please refer to: https://gpiozero.readthedocs.io/en/stable/api_input.html#smoothedinputdevice

.. include:: ../common/com.Infrared Obstacle Avoidance Sensor_2.rst

Code
================================================================

Python Code 30.2.1 Alertor
----------------------------------------------------------------

First observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:`  support@freenove.com

1.  Use ``cd`` command to enter 30.2.1_Alertor directory of Python code

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/Python_GPIOZero_Code/30.2.1_Alertor

2.  Use python command to execute code ``Alertor.py``

.. code-block:: console

    $ python Alertor.py

After the program is executed, when you block the sensor with your hand at a certain distance or the sensor encounters an obstacle, the buzzer will sound a reminder, and the LED will flash to remind you.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/30.2.1_Alertor/Alertor.py
    :linenos: 
    :language: python
