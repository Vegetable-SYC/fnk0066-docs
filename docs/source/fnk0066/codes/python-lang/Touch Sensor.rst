################################################################
Chapter Touch Sensor 
################################################################

.. include:: ../common/com.Touch Sensor TTP223_1.rst

Code
================================================================

Python Code 27.1.1 TouchSensor
----------------------------------------------------------------

.. hint:: 
    :red:`If you have any concerns, please contact us via:`  support@freenove.com

1.  Use cd command to enter 27.1.1_TouchSensor directory of Python code. 

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/Python_GPIOZero_Code/27.1.1_TouchSensor

2.  Use Python command to execute code " TouchSensor.py".

.. code-block:: console

    $ ython TouchSensor.py

In this code, we use the touch sensor to adjust the brightness of the LED. Every time you touch the sensor with your hand, the brightness of the LED changes.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/27.1.1_TouchSensor/TouchSensor.py
    :linenos: 
    :language: python

Import the TouchSensor class from the sensor module. TouchSensor is similar to the MotionSensor class in the GPIO Zero library in that they both actually use the SmoothedInputDevice class.

.. code-block:: python

    from sensor import TouchSensor

sensor.when_touch associates the touch sensor pin with SensorEven(). When SensorPin detects a high level, the SensorEven() function is called and executed. That is, every time the sensor is touched, a variable called grade is used to record the number of touches.

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/27.1.1_TouchSensor/TouchSensor.py
    :linenos: 
    :language: python
    :lines: 18-27

Set the LED light to emit different brightness according to the value of grade.

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/27.1.1_TouchSensor/TouchSensor.py
    :linenos: 
    :language: python
    :lines: 30-41

sensor.py

Import the SmoothedInputDevice class from the GPIO Zero library, create the TouchSensor class, and initialize the parametersImport the SmoothedInputDevice class from the GPIO Zero library, create the TouchSensor class, and initialize the parameters

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/27.1.1_TouchSensor/sensor.py
    :linenos: 
    :language: python

.. seealso::

    For more information about the methods used by the SmoothedInputDevice class in the GPIO Zero library,please refer to: https://gpiozero.readthedocs.io/en/stable/api_input.html#smoothedinputdevice

.. include:: ../common/com.Touch Sensor TTP223_2.rst

Code
================================================================

Python Code 27.2.1 Discolor
----------------------------------------------------------------

First, observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:`  support@freenove.com

1.  Use cd command to enter 27.2.1_Discolor directory of Python code.

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/Python_GPIOZero_Code/27.2.1_Discolor

2.  Use Python command to execute code " Discolor.py ".

.. code-block:: console

    $ python Discolor.py

After the program is executed, we can use the touch sensor to adjust the color change of the RGB LED. Every time the sensor is touched, the color of the RGB LED changes. Color changes from red to green to blue.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/27.2.1_Discolor/Discolor.py
    :linenos: 
    :language: python

GPIO.add_event_detect() associates the touch sensor pin with SensorEven(). When SensorPin detects a high level, the SensorEven() function is called and executed.

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/27.2.1_Discolor/Discolor.py
    :linenos: 
    :language: python
    :lines: 18-23

Determine the number of times the sensor is pressed, and control the pin R, G, and B to output different PWM values, thereby controlling the color of the RGB LED.

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/27.2.1_Discolor/Discolor.py
    :linenos: 
    :language: python
    :lines: 29-40
