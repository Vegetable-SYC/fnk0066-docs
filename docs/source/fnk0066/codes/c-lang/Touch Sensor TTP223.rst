##############################################################################
Chapter Touch Sensor TTP223
##############################################################################

.. include:: ../common/com.Touch Sensor TTP223_1.rst

Code
================================================================

C Code 27.1.1 TouchSensor
----------------------------------------------------------------

First, observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:` support@freenove.com

1.  Use ``cd`` command to enter 27.1.1_TouchSensor directory of C code.

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/C_Code/27.1.1_TouchSensor

2.  Use following command to compile ``TouchSensor.c`` and generate executable file ``TouchSensor``.

.. code-block:: console

    $ gcc TouchSensor.c -o TouchSensor -lwiringPi

3.  Run the generated file ``TouchSensor``.

.. code-block:: console

    $ sudo ./TouchSensor

In this code, we use the touch sensor to adjust the brightness of the LED. Every time you touch the sensor with your hand, the brightness of the LED changes.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/27.1.1_TouchSensor/TouchSensor.c
    :linenos: 
    :language: C

Read the signal pin of the touch sensor, and determine whether the state of the touch sensor has changed. If it has changed, record the time point.

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/27.1.1_TouchSensor/TouchSensor.c
    :linenos: 
    :language: C
    :lines: 28-31

Check whether the state of the touch sensor is consistent with the previous moment every captureTime milliseconds. If not, assign the state of the touch sensor to the touch sensor variable SensorState.

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/27.1.1_TouchSensor/TouchSensor.c
    :linenos: 
    :language: C
    :lines: 34-37

Each time the sensor is touched, a variable grade is used to record the number of touches.

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/27.1.1_TouchSensor/TouchSensor.c
    :linenos: 
    :language: C
    :lines: 36-43

Set the LED light to emit different brightness according to the value of grade.

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/27.1.1_TouchSensor/TouchSensor.c
    :linenos: 
    :language: C
    :lines: 45-59

.. include:: ../common/com.Touch Sensor TTP223_2.rst

Code
================================================================

C Code 27.2.1 Discolor
----------------------------------------------------------------

First, observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:` support@freenove.com

1.  Use ``cd`` command to enter 27.2.1_Discolor directory of C code.

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/C_Code/27.2.1_Discolor

2.  Use following command to compile ``Discolor.c`` and generate executable file ``Discolor``. 

.. code-block:: console

    $ gcc Discolor.c -o Discolor -lwiringPi

3.  Run the generated file ``Discolor``.

.. code-block:: console

    $ sudo ./Discolor

After the program is executed, we can use the touch sensor to adjust the color change of the RGB LED. Every time the sensor is touched, the color of the RGB LED changes. Color changes from red to green to blue.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/27.2.1_Discolor/Discolor.c
    :linenos: 
    :language: C

Define a function called setupLedPin() to initialize the PWM configuration of the R, G, and B pins.

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/27.2.1_Discolor/Discolor.c
    :linenos: 
    :language: C
    :lines: 23-28

Determine the number of times the sensor is pressed, and control the pin R, G, and B to output different PWM values, thereby controlling the color of the RGB LED.

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/27.2.1_Discolor/Discolor.c
    :linenos: 
    :language: C
    :lines: 65-71
