##############################################################################
Chapter Infrared Obstacle Avoidance Sensor
##############################################################################

.. include:: ../common/com.Infrared Obstacle Avoidance Sensor_1.rst

Code
================================================================

C Code 30.1.1 InfraredSensor
----------------------------------------------------------------

First observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:` support@freenove.com

1.  Use ``cd`` command to enter 30.1.1_InfraredSensor directory of C code.

.. code-block:: console    
    
    $ cd ~/Freenove_Kit/Code/C_Code/30.1.1_InfraredSensor

2.  Use following command to compile ``InfraredSensor.c`` and generate executable file ``InfraredSensor``.

.. code-block:: console    
    
    $ gcc InfraredSensor.c -o InfraredSensor -lwiringPi

3.  Run the generated file ``InfraredSensor``

.. code-block:: console    
    
    $ sudo ./InfraredSensor

After the program is executed, when you block the sensor with your hand at a certain distance or the sensor encounters an obstacle, the LED will turn on, and when the sensor is not blocked or the sensor does not encounter an obstacle, the LED will turn off.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/30.1.1_InfraredSensor/InfraredSensor.c
    :linenos: 
    :language: C

.. include:: ../common/com.Infrared Obstacle Avoidance Sensor_2.rst

Code
================================================================

C Code 30.2.1 Alertor
----------------------------------------------------------------

First observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:` support@freenove.com

1.  Use ``cd`` command to enter 30.2.1_Alertor directory of C code.

.. code-block:: console    
    
    $ cd ~/Freenove_Kit/Code/C_Code/30.2.1_Alertor

2.  Use following command to compile ``Alertor.c`` and generate executable file ``Alertor``.

.. code-block:: console    
    
    $ gcc Alertor.c -o Alertor -lwiringPi

3.  Run the generated file ``Alertor``

.. code-block:: console    
    
    $ sudo ./Alertor

After the program is executed, when you block the sensor with your hand at a certain distance or the sensor encounters an obstacle, the buzzer will sound a reminder, and the LED will flash to remind you.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/30.2.1_Alertor/Alertor.c
    :linenos: 
    :language: C
