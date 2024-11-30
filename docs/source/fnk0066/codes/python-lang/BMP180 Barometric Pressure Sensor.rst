################################################################
Chapter BMP180 Barometric Pressure Sensor
################################################################

.. include:: ../common/com.BMP180 Barometric Pressure Sensor.rst

Code
================================================================

Python Code 33.1.1 Barometer
----------------------------------------------------------------

If you did not configure I2C and Install Smbus, please refer to :doc:`Chapter 7 ADC <ADC>`. If you did, please move on.

First observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:`  support@freenove.com

1.  Make sure you have set python3 as default python. Then use cd command to enter 33.1.1_Barometer directory of Python code.

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/Python_GPIOZero_Code/33.1.1_Barometer

2.  Use python command to execute code ``Barometer.py``

.. code-block:: console

    $ python Barometer.py

After the program is executed, the terminal will display the current air pressure value, temperature value and altitude.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/33.1.1_Barometer/Barometer.py
    :linenos: 
    :language: python

The function bmp180_GetTemperature() is used to calculate the current temperature value.

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/33.1.1_Barometer/Barometer.py
    :linenos: 
    :language: python
    :lines: 97-103

The function bmp180_GetPressure() is used to calculate the current pressure value.

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/33.1.1_Barometer/Barometer.py
    :linenos: 
    :language: python
    :lines: 104-129
    

The function bmp180_Altitude() is used to calculate the current altitude.

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/33.1.1_Barometer/Barometer.py
    :linenos: 
    :language: python
    :lines: 130-133