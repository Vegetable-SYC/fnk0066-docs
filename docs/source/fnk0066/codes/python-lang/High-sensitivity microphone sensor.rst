################################################################
Chapter High-sensitivity microphone sensor
################################################################

.. include:: ../common/com.High-sensitivity microphone sensor.rst

Code
================================================================

Python Code 26.1.1 VoiceLamp
----------------------------------------------------------------

First observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:`  support@freenove.com

1.  Use ``cd`` command to enter 26.1 1_VoiceLamp directory of Python code.

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/Python_GPIOZero_Code/26.1.1_VoiceLamp

2.  Use python command to execute code ``VoiceLamp.py``

.. code-block:: console

    $ python VoiceLamp.py

After the program is executed, when you speak to the sensor, the LED will turn on for 5 seconds. After 5 seconds, the LED will turn off. When the sensor does not recognize the sound, the LED will turn off.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/26.1.1_VoiceLamp/VoiceLamp.py
    :linenos: 
    :language: python

Import the MicrophoneSensor class from the sensor module. MicrophoneSensor is similar to the MotionSensor class in the GPIO Zero library in that they both actually use the SmoothedInputDevice class.

.. code-block:: python

    from sensor import MicrophoneSensor

Read the signal pin of the high-sensitivity microphone sensor to determine whether the state of the sensor is high. When the sensor recognizes the sound, it outputs a high level, the variable sensor.is_active is True, and the LED will turn on for 5 seconds and then turn off.

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/26.1.1_VoiceLamp/VoiceLamp.py
    :linenos: 
    :language: python
    :lines: 17-26

sensor.py

Import the SmoothedInputDevice class from the GPIO Zero library, create the MicrophoneSensor class, and initialize the parameters.

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/26.1.1_VoiceLamp/sensor.py
    :linenos: 
    :language: python

.. seealso::

    For more information about the methods used by the SmoothedInputDevice class in the GPIO Zero library,please refer to:https://gpiozero.readthedocs.io/en/stable/api_input.html#smoothedinputdevice
