##############################################################################
Chapter Soldering a Circuit Board
##############################################################################

.. include:: ../common/com.Soldering a Circuit Board_1.rst

Code
================================================================

This now will be the third time we have made the Flowing Water Light. In this project, we will solder a completely new circuit for Flowing Water Light. Additionally, the program is also different from the previous ones we have used. When this light flows, it will have a long “tail”.

C Code 35.2.1 LightWater03
----------------------------------------------------------------

First, observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:` support@freenove.com

1.	Use ``cd`` command to enter 35.2.1_LightWater03 directory of C code.

.. code-block:: console    
    
    $ cd ~/Freenove_Kit/Code/C_Code/35.2.1_LightWater03

2.	Use following command to compile ``LightWater03.c`` and generate executable file ``LightWater03``.

.. code-block:: console    
    
    $ gcc LightWater03.c  -o LightWater03  -lwiringPi

3.	Then run the generated file ``LightWater03``.

.. code-block:: console    
    
    $ sudo ./LightWater03

After the program is executed, the LEDs will light up in the form of flowing water with a long “tail”.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/35.2.1_LightWater03/LightWater03.c
    :linenos: 
    :language: C

We can see that this program is different from the previous one that we had used. We define an array to modulate different PWM pulse widths for LEDs, in doing so different LEDs can emit varied brightness. Starting from the array index 0, take an array of 8 adjacent numbers as the LED duty cycle and output it one at a time. Increasing the starting index number in turn, then it will create a flowing effect.

.. code-block:: c

    const int pluseWidth[]={0,0,0,0,0,0,0,0,64,32,16,8,4,2,1,0,0,0,0,0,0,0,0};

By recording the moving time point to control the speed of the movement of index number, controls the speed of the Flowing Water Light. Variable moveSpeed saves the time interval of each move, and the greater the value is, the slower the rate of the flowing movement (the reverse creates faster flowing movement).

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/35.2.1_LightWater03/LightWater03.c
    :linenos: 
    :language: C
    :lines: 38-42

Finally, in a “for” loop with i=64, modulate the output pulse width of the PWM square wave. The process, from the beginning of implementing the for loop to the end, is a PWM cycle. In the loop, there is another for loop with j=8 and in this loop, it compares the number “i” to the value of the array to determine output high or low level. Then, the data will be sent to the 74HC595 IC Chip.

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/35.2.1_LightWater03/LightWater03.c
    :linenos: 
    :language: C
    :lines: 43-51
