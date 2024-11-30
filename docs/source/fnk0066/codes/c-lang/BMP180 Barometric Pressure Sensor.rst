##############################################################################
Chapter BMP180 Barometric Pressure Sensor
##############################################################################

.. include:: ../common/com.BMP180 Barometric Pressure Sensor.rst

Code
================================================================

C Code 33.1.1 Barometer
----------------------------------------------------------------

If you did not **configure I2C and Install Smbus**, please refer to :ref:`Chapter 7<ADC>`. If you did, please move on.

First observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:` support@freenove.com

1.  Use cd command to enter 33.1.1_Barometer directory of C code.

.. code-block:: console    
    
    $ cd ~/Freenove_Kit/Code/C_Code/33.1.1_Barometer

2.  Use following command to compile "Barometer.c" and generate executable file "Barometer ".

.. code-block:: console    
    
    $ gcc -o Barometer ./smbus.c ./Barometer.c -lm

3.  Run the generated file "Barometer "

.. code-block:: console    
    
    $ sudo ./Barometer

After the program is executed, the terminal will display the current air pressure value, temperature value and altitude.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/33.1.1_Barometer/Barometer.c
    :linenos: 
    :language: C

The function bmp180_GetTemperature() is used to calculate the current temperature value.


.. literalinclude:: ../../../freenove_Kit/Code/C_Code/33.1.1_Barometer/Barometer.c
    :linenos: 
    :language: C
    :lines: 150-157

The function bmp180_GetPressure() is used to calculate the current pressure value.

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/33.1.1_Barometer/Barometer.c
    :linenos: 
    :language: C
    :lines: 123-147

The function bmp180_Altitude() is used to calculate the current altitude.   

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/33.1.1_Barometer/Barometer.c
    :linenos: 
    :language: C
    :lines: 161-168

