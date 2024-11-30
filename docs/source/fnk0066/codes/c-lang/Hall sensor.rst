##############################################################################
Chapter Hall sensor
##############################################################################

.. include:: ../common/com.Hall sensor_1.rst

Code
================================================================

C Code 29.1.1 HallSensor
----------------------------------------------------------------

First observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:` support@freenove.com

1.  Use cd command to enter 29.1.1_HallSensor directory of C code.

.. code-block:: console    
    
    $ cd ~/Freenove_Kit/Code/C_Code/29.1.1_HallSensor

2.  Use following command to compile " HallSensor.c" and generate executable file "HallSensor".

.. code-block:: console    
    
    $ gcc HallSensor.c -o HallSensor -lwiringPi

3.  Run the generated file "HallSensor"

.. code-block:: console    
    
    $ sudo ./HallSensor


After the program is executed, when the sensor is close to the magnetic field (horn) by hand, the LED will turn on, and if the sensor does not sense the magnetic field (horn), the LED will turn off.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/29.1.1_HallSensor/HallSensor.c
    :linenos: 
    :language: C


.. include:: ../common/com.Hall sensor_2.rst

Code
================================================================

C Code 29.2.1 Alertor
----------------------------------------------------------------

First observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:` support@freenove.com

1.  Use ``cd`` command to enter 29.2.1_Alertor directory of C code.

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/C_Code/29.2.1_Alertor

2.  Use following command to compile ``Alertor.c`` and generate executable file ``Alertor``.

.. code-block:: console

    $ gcc Alertor.c -o Alertor -lwiringPi

3.  Run the generated file ``Alertor``

.. code-block:: console

    $ sudo ./Alertor

After the program is executed, every time the sensor is close to the magnetic field (speaker) by hand, the buzzer will sound an alarm, and the LED will flash to remind.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/29.2.1_Alertor/Alertor.c
    :linenos: 
    :language: C

