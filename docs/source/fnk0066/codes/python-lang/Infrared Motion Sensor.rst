################################################################
Chapter Infrared Motion Sensor
################################################################

.. include:: ../common/com.Infrared Motion Sensor.rst

Code
================================================================

In this project, we will use the Infrared Motion Sensor to trigger an LED, essentially making the Infrared Motion sensor act as a Motion Switch. Therefore, the code is very similar to the earlier project "Push Button Switch and LED”. The difference is that, when Infrared Motion Sensor detects change, it will output high level; when button is pressed, it will output low level. When the sensor output high level, the LED turns ON, or it will turn OFF.

Python Code 23.1.1 SenseLED
----------------------------------------------------------------

First, observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:`  support@freenove.com

1.	Use cd command to enter 22.1.1_MatrixKeypad directory of Python code.

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/Python_GPIOZero_Code/23.1.1_SenseLED

2.	Use Python command to execute code "SenseLED.py".

.. code-block:: console

    $ python SenseLED.py

After the program is executed, wait 1 minute for initialization. Then move away from or move closer to the Infrared Motion Sensor and observe whether the LED turns ON or OFF. The Terminal window will continuously display the state of LED. As is shown below:

.. image:: ../_static/imgs/Infrared_LED.png
    :align: center

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/23.1.1_SenseLED/SenseLED.py
    :linenos: 
    :language: python

For more information about the methods used by the MotionSensor class in the GPIO Zero library,please refer to: https://gpiozero.readthedocs.io/en/stable/api_input.html#motionsensor-d-sun-pir

