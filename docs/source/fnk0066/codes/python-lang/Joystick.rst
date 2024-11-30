################################################################
Chapter Joystick
################################################################

.. include:: ../common/com.Joystick.rst

Code
================================================================

In this project's code, we will read the ADC values of X and Y axes of the Joystick, and read digital quality of the Z axis, then display these out in Terminal.

Python Code 12.1.1 Joystick
----------------------------------------------------------------

If you did not configure I2C, please refer to :doc:`Chapter 7 ADC <ADC>`. If you did, please continue.

First, observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:`  support@freenove.com

1.	Use cd command to enter 12.1.1_Joystick directory of Python code.

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/Python_GPIOZero_Code/12.1.1_Joystick

2.	Use Python command to execute Python code "Joystick.py". 

.. code-block:: console

    $ python Joystick.py

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/12.1.1_Joystick/Joystick.py
    :linenos: 
    :language: python

In the code, configure Z_Pin as pull-up input mode. In the while loop, use analogRead() to read the values of the axes X and Y and use the variable val_Z to save the value of the button.value variable for the Z axis, and then display them. When the button is pressed, the value of the variable button.value is 1, otherwise the value is 0.

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/12.1.1_Joystick/Joystick.py
    :linenos: 
    :language: python
    :lines: 28-34

For more information about the methods used by the Button class in the GPIO Zero library,please refer to:
https://gpiozero.readthedocs.io/en/stable/api_input.html#button
