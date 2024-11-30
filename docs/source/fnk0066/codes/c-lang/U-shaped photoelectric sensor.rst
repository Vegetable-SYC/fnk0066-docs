##############################################################################
Chapter U-shaped photoelectric sensor
##############################################################################

.. include:: ../common/com.U-shaped photoelectric sensor_1.rst

Code
================================================================

C Code 28.1.1 PhotoSensor
----------------------------------------------------------------

First observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:` support@freenove.com

1.  Use cd command to enter 28.1.1_PhotoSensor directory of C code.

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/C_Code/28.1.1_PhotoSensor

2.  Use following command to compile " PhotoSensor.c" and generate executable file "PhotoSensor".

.. code-block:: console

    $ gcc PhotoSensor.c -o PhotoSensor -lwiringPi

3.  Run the generated file " PhotoSensor"

.. code-block:: console

    $ sudo ./PhotoSensor    

When you use the module whose output signal is low level, after the program is executed, when the photoelectric sensor is blocked, the LED lights up, when the photoelectric sensor is not blocked, the LED turns off.

When you use the module whose output signal is low level, after the program is executed, when the photoelectric sensor is blocked, the LED lights up, when the photoelectric sensor is not blocked, the LED turns off.

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/28.1.1_PhotoSensor/PhotoSensor.c
    :linenos: 
    :language: C

.. include:: ../common/com.U-shaped photoelectric sensor_2.rst

Code
================================================================

C Code 28.2.1 Alertor
----------------------------------------------------------------

First observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:` support@freenove.com

1.  Use ``cd`` command to enter 28.2.1_Alertor directory of C code.

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/C_Code/28.2.1_Alertor

2.  Use following command to compile ``Alertor.c`` and generate executable file ``Alertor``.

.. code-block:: console

    $ gcc Alertor.c -o Alertor -lwiringPi

3.  Run the generated file ``Alertor``

.. code-block:: console

    $ sudo ./Alertor

After the program is executed, every time the U-shaped photoelectric sensor is blocked by hand, the buzzer will sound an alarm, and the LED will flash to remind.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/28.2.1_Alertor/Alertor.c
    :linenos: 
    :language: C

The wiringPiISR() function associates the sensor pins with sensorEven().Because there are high level triggering module and low level triggering module in the U-type photoelectric sensor, we use the double-edge detection method here to make the program compatible with the module in your hand. When sensorPin detects low level or high level, it will call and execute the sensorEven() function.

.. code-block:: c

    wiringPiISR(sensorPin,INT_EDGE_BOTH,&sensorEven);
    void sensorEven(void){
        alarm(3);
    }

The function alarm() is used to control the active buzzer to emit an alarm sound and control the LED to flash at the same time. Use variable times to pass in the number of times the alarm sounds and the LED blinks.

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/28.2.1_Alertor/Alertor.c
    :linenos: 
    :language: C
    :lines: 14-23

.. c:function:: int wiringPiISR (int pin, int edgeType, void (*function)(void)) ;

    This is an interrupt detection function. The first parameter specifies the IO port to detect. The second parameter specifies the trigger method to detect. The third parameter specifies the function name. The function will be executed when the specified action is detected.
    
    The following are common detection triggers:
    
    **INT_EDGE_FALLING**: falling edge trigger 
    
    **INT_EDGE_RISING**: rising edge trigger 
    
    **INT_EDGE_BOTH**: triggers both up and down
