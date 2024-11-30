##############################################################################
Chapter Infrared Motion Sensor
##############################################################################

.. include:: ../common/com.Infrared Motion Sensor.rst

Code
================================================================

In this project, we will use the Infrared Motion Sensor to trigger an LED, essentially making the Infrared Motion sensor act as a Motion Switch. Therefore, the code is very similar to the earlier project "Push Button Switch and LED”. The difference is that, when Infrared Motion Sensor detects change, it will output high level; when button is pressed, it will output low level. When the sensor output high level, the LED turns ON, or it will turn OFF.

C Code 23.1.1 SenseLED
----------------------------------------------------------------

First, observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:` support@freenove.com

1.	Use ``cd`` command to enter 23.1.1_SenseLED directory of C code.

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/C_Code/23.1.1_SenseLED

2.	Use following command to compile ``SenseLED.c`` and generate executable file ``SenseLED``.

.. code-block:: console

    $ gcc SenseLED.c -o SenseLED -lwiringPi

3.	Run the generated file ``SenseLED``.

.. code-block:: console

    $ sudo ./SenseLED

After the program is executed, wait 1 minute for initialization. Then move away from or move closer to the Infrared Motion Sensor and observe whether the LED turns ON or OFF. The Terminal window will continuously display the state of LED. As is shown below:

.. image:: ../_static/imgs/Infrared_LED.png
    :align: center

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/23.1.1_SenseLED/SenseLED.c
    :linenos: 
    :language: C

It can be seen that the code is based on the same principles of the "ButtonLED" code in addition to determining the level of the input signal.