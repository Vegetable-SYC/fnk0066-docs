################################################################
Chapter Stepper Motor
################################################################

.. include:: ../common/com.Stepper Motor.rst

Code
================================================================

Python Code 16.1.1 SteppingMotor
----------------------------------------------------------------

First, observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:`  support@freenove.com

1.	Use cd command to enter 16.1.1_SteppingMotor directory of Python code.

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/Python_GPIOZero_Code/16.1.1_SteppingMotor

2.	Use Python command to execute code "SteppingMotor.py".

.. code-block:: console

    $ python SteppingMotor.py

After the program is executed, the Stepper Motor will rotate 360° clockwise and then 360° anticlockwise and repeat this action in an endless loop.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/16.1.1_SteppingMotor/SteppingMotor.py
    :linenos: 
    :language: python

In the code we define the four pins of the Stepper Motor and the order to supply power to the coils for a four-step rotation mode.

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/16.1.1_SteppingMotor/SteppingMotor.py
    :linenos: 
    :language: python
    :lines: 11-15

Subfunction **moveOnePeriod** ((int dir, int ms) will drive the Stepper Motor rotating four-step clockwise or anticlockwise, four-step as a cycle. Where parameter "dir" indicates the rotation direction, if "dir" is 1, the servo will rotate clockwise, otherwise it rotates to anticlockwise. Parameter "ms" indicates the time between each two steps. The "ms" of Stepper Motor used in this project is 3ms (the shortest time period), a value of less than 3ms will exceed the limits of the Stepper Motor with a result that it does not rotate.

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/16.1.1_SteppingMotor/SteppingMotor.py
    :linenos: 
    :language: python
    :lines: 18-27

Subfunction **moveSteps** (direction, ms, steps) is used to specify the cycle number of Stepper Motor.

.. code-block:: python

    def moveSteps(direction, ms, steps):
        for i in range(steps):
            moveOnePeriod(direction, ms)

Subfunction **motorStop** () is used to stop the Stepper Motor.

.. code-block:: python

    def motorStop():
        for i in range(0,4,1):
            motors.off()

Finally, in the while loop of main function, rotate one revolution clockwise, and then one revolution anticlockwise. According to the previous material covered, the Stepper Motor one revolution requires 2048 steps, that is, 2048/4=512 cycle.

.. code-block:: python

    while True:
        moveSteps(0,3,512)  # rotating 360 deg clockwise, a total of 2048 steps in a circle, 512 cycles
        time.sleep(0.5)
        moveSteps(1,3,512)  # rotating 360 deg anticlockwise
        time.sleep(0.5)

For more information about the methods used by the OutputDevice class in the GPIO Zero library,please refer to: 
https://gpiozero.readthedocs.io/en/stable/api_output.html#outputdevice