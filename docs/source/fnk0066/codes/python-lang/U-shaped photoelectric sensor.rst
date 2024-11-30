################################################################
Chapter U-shaped photoelectric sensor
################################################################

.. include:: ../common/com.U-shaped photoelectric sensor_1.rst

Code
================================================================

Python Code 28.1.1 PhotoSensor
----------------------------------------------------------------

First observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:`  support@freenove.com

1.  Use ``cd`` command to enter 28.1.1 1_Photosensor directory of Python code.

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/Python_GPIOZero_Code/28.1.1_PhotoSensor

2.  Use python command to execute code ``PhotoSensor.py``

.. code-block:: console

    $ python  PhotoSensor.py

When you use the module whose output signal is low level, after the program is executed, when the photoelectric sensor is blocked, the LED lights up, when the photoelectric sensor is not blocked, the LED turns off.

When you use the module with high output signal, the LED will be off when the photoelectric sensor is blocked and on when the photoelectric sensor is not blocked after the program is executed.

The phenomena are opposite, depending on the module in your hand.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/28.1.1_PhotoSensor/PhotoSensor.py
    :linenos: 
    :language: python

Import the PhotoSensor class from the sensor module. PhotoSensor is similar to the MotionSensor class in the GPIO Zero library in that they both actually use the SmoothedInputDevice class.

.. code-block:: python

    from sensor import PhotoSensor

.. seealso::

    For more information about the methods used by the SmoothedInputDevice class in the GPIO Zero library,please refer to: https://gpiozero.readthedocs.io/en/stable/api_input.html#smoothedinputdevice

.. include:: ../common/com.U-shaped photoelectric sensor_2.rst

Code
================================================================

Python Code 28.2.1 Alertor
----------------------------------------------------------------

First observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:`  support@freenove.com

1.  Use ``cd`` command to enter 28.2.1_Alertor directory of Python code

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/Python_GPIOZero_Code/28.2.1_Alertor

2.  Use python command to execute code ``Alertor.py``

.. code-block:: console

    $ python Alertor.py

After the program is executed, every time the U-shaped photoelectric sensor is blocked by hand, the buzzer will sound an alarm, and the LED will flash to remind.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/28.2.1_Alertor/Alertor.py
    :linenos: 
    :language: python

The sensor.when_occlusion and sensor.when_no_occlusion functions associate the sensor pin with sensorEven().Because there are high level triggering module and low level triggering module in the U-type photoelectric sensor, we use the double-edge detection method here to make the program compatible with the module in your hand. When sensorPin detects low level or high level, it will call and execute the sensorEven() function.

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/28.2.1_Alertor/Alertor.py
    :linenos: 
    :language: python
    :lines: 30-36

The function alarm() is used to control the active buzzer to emit an alarm sound and control the LED to flash at the same time. Use variable times to pass in the number of times the alarm sounds and the LED blinks.

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/28.2.1_Alertor/Alertor.py
    :linenos: 
    :language: python
    :lines: 19-28