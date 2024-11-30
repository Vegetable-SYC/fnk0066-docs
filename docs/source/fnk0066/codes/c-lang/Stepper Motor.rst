##############################################################################
Chapter Stepper Motor
##############################################################################

.. include:: ../common/com.Stepper Motor.rst

Code
================================================================

C Code 16.1.1 SteppingMotor
----------------------------------------------------------------

First, observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:` support@freenove.com

1.	Use ``cd`` command to enter 16.1.1_SteppingMotor directory of C code.

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/C_Code/16.1.1_SteppingMotor

2.	Use following command to compile ``SteppingMotor.c`` and generate executable file ``SteppingMotor``. 

.. code-block:: console

    $ gcc SteppingMotor.c -o SteppingMotor -lwiringPi

3.	Run the generated file ``SteppingMotor``.

.. code-block:: console

    $ sudo ./SteppingMotor

After the program is executed, the Stepper Motor will rotate 360° clockwise and then 360° anticlockwise and repeat this action in an endless loop.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/16.1.1_SteppingMotor/SteppingMotor.c
    :linenos: 
    :language: C

In the code we define the four pins of the Stepper Motor and the order to supply power to the coils for a four-step rotation mode.

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/16.1.1_SteppingMotor/SteppingMotor.c
    :linenos: 
    :language: C
    :lines: 10-12

Subfunction moveOnePeriod ((int dir,int ms) will drive the Stepper Motor rotating four-step clockwise or anticlockwise, four-step as a cycle. Where parameter "dir" indicates the rotation direction, if "dir" is 1, the servo will rotate clockwise, otherwise it rotates to anticlockwise. Parameter "ms" indicates the time between each two steps. The "ms" of Stepper Motor used in this project is 3ms (the shortest time period), a value of less than 3ms will exceed the limits of the Stepper Motor with a result that it does not rotate.

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/16.1.1_SteppingMotor/SteppingMotor.c
    :linenos: 
    :language: C
    :lines: 14-29

Subfunction moveSteps (int dir, int ms, int steps) is used to specific cycle number of Stepper Motor.

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/16.1.1_SteppingMotor/SteppingMotor.c
    :linenos: 
    :language: C
    :lines: 31-36

Subfunction motorStop () is used to stop the Stepper Motor.

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/16.1.1_SteppingMotor/SteppingMotor.c
    :linenos: 
    :language: C
    :lines: 37-42

Finally, in the while loop of main function, rotate one revolution clockwise, and then one revolution anticlockwise. According to the previous material covered, the Stepper Motor one revolution requires 2048 steps, that is, 2048/4=512 cycle.

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/16.1.1_SteppingMotor/SteppingMotor.c
    :linenos: 
    :language: C
    :lines: 54-59
