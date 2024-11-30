##############################################################################
Chapter Servo
##############################################################################

.. include:: ../common/com.Servo.rst

Code
================================================================

In this project, we will make a Servo rotate from 0 degrees to 180 degrees and then reverse the direction to make it rotate from 180 degrees to 0 degrees and repeat these actions in an endless loop.

C Code 15.1.1 Sweep
----------------------------------------------------------------

First, observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:` support@freenove.com

1.	Use ``cd`` command to enter 15.1.1_Sweep directory of C code.

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/C_Code/15.1.1_Sweep

2.	Use following command to compile ``Sweep.c`` and generate executable file ``Sweep``. 

.. code-block:: console

    $ gcc Sweep.c -o Sweep -lwiringPi

3.	Run the generated file ``Sweep``.

.. code-block:: console

    $ sudo ./Sweep

After the program is executed, the Servo will rotate from 0 degrees to 180 degrees and then reverse the direction to make it rotate from 180 degrees to 0 degrees and repeat these actions in an endless loop.
The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/15.1.1_Sweep/Sweep.c
    :linenos: 
    :language: C

A 50 Hz pulse for a 20ms cycle is required to control the Servo. In function softPwmCreate (int pin, int initialValue, int pwmRange), the unit of the third parameter pwmRange is 100US, specifically 0.1ms. In order to get the PWM with a 20ms cycle, the pwmRange shoulde be set to 200. So in the subfunction of servoInit (), we create a PWM pin with a pwmRange of 200.

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/15.1.1_Sweep/Sweep.c
    :linenos: 
    :language: C
    :lines: 18-20

Since 0-180 degrees of the Servo's motion corresponds to the PWM pulse width of 0.5-2.5ms, with a PwmRange of 200 ms. We then need the function softPwmWrite (int pin, int value) and the scope 5-25 of the parameter values to correspond to 0-180 degrees’ motion of the Servo. What’s more, the number written in subfunction servoWriteMS () should be within the range of 5-25. However, in practice, due to the inherent error manufactured into each Servo, the pulse width will have a deviation. So we need to define a minimum and maximum pulse width and an error offset (this is essential in robotics).

.. code-block:: c

    #define OFFSET_MS 3     //Define the unit of servo pulse offset: 0.1ms
    #define SERVO_MIN_MS 5+OFFSET_MS        //define the pulse duration for minimum angle of servo
    #define SERVO_MAX_MS 25+OFFSET_MS       //define the pulse duration for maximum angle of servo
    .......
    void servoWriteMS(int pin, int ms){
        if(ms > SERVO_MAX_MS)
            ms = SERVO_MAX_MS;
        if(ms < SERVO_MIN_MS)
            ms = SERVO_MIN_MS;
        softPwmWrite(pin,ms);
    }

In subfunction servoWrite (), directly input an angle value (0-180 degrees), map the angle to the pulse width and then output it.

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/15.1.1_Sweep/Sweep.c
    :linenos: 
    :language: C
    :lines: 21-27

Finally, in the "while" loop of the main function, use two "for" cycle to make servo rotate from 0 degrees to 180 degrees, and then from 180 degrees to 0 degrees.

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/15.1.1_Sweep/Sweep.c
    :linenos: 
    :language: C
    :lines: 44-55
