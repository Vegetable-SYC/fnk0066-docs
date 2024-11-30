##############################################################################
Chapter Rotary Encoder
##############################################################################

.. include:: ../common/com.Rotary Encoder_1.rst

Code
================================================================

C Code 31.1.1 RotaryEncoder
----------------------------------------------------------------

First observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:` support@freenove.com

1.  Use ``cd`` command to enter 31.1.1_RotaryEncoder directory of C code.

.. code-block:: console    
    
    $ cd ~/Freenove_Kit/Code/C_Code/31.1.1_RotaryEncoder

2.  Use following command to compile ``RotaryEncoder.c`` and generate executable file ``RotaryEncoder``.

.. code-block:: console    
    
    $ gcc RotaryEncoder.c -o RotaryEncoder -lwiringPi

3.  Run the generated file ``RotaryEncoder``.

.. code-block:: console    
    
    $ sudo ./RotaryEncoder

After the program is executed, the rotary encoder can count the number of output pulses during the forward and reverse rotation. When the rotary encoder is rotated clockwise by hand, the count value will increase. When the rotary encoder is rotated counterclockwise by hand , the count value will decrease. When the rotary encoder is pressed by hand, it can be reset to the initial state, that is, the count starts from 0.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/31.1.1_RotaryEncoder/RotaryEncoder.c
    :linenos: 
    :language: C

Function rotaryDeal() is used to determine whether the rotary encoder is rotating, and when there is rotation, determine whether it is rotating clockwise or counterclockwise. Use variable previousCounterValue to record the number of rotations. When rotating clockwise, the variable increases, and when rotating counterclockwise, the variable decreases.

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/31.1.1_RotaryEncoder/RotaryEncoder.c
    :linenos: 
    :language: C
    :lines: 19-38

Read the SW signal pin of the rotary encoder, and determine whether the rotary encoder is pressed. If it is pressed, the variable previousCounterValue is cleared.

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/31.1.1_RotaryEncoder/RotaryEncoder.c
    :linenos: 
    :language: C
    :lines: 51-56

.. include:: ../common/com.Rotary Encoder_2.rst

Code
================================================================

C Code 31.2.1 Dimmable
----------------------------------------------------------------

First observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:` support@freenove.com

1.  Use ``cd`` command to enter 30.2.1_Dimmable directory of C code.

.. code-block:: console    
    
    $ cd ~/Freenove_Kit/Code/C_Code/31.2.1_Dimmable

2.  Use following command to compile ``Dimmable.c`` and generate executable file ``Dimmable``.

.. code-block:: console    
    
    $ gcc Dimmable.c -o Dimmable -lwiringPi

3.  Run the generated file ``Dimmable``

.. code-block:: console    
    
    $ sudo ./Dimmable

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/31.2.1_Dimmable/Dimmable.c
    :linenos: 
    :language: C

Function rotaryDeal() is used to determine whether the rotary encoder is rotating, and when there is rotation, determine whether it is rotating clockwise or counterclockwise. Use variable previousCounterValue to record the number of rotations. When rotating clockwise, the variable increases, and when rotating counterclockwise, the variable decreases.

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/31.2.1_Dimmable/Dimmable.c
    :linenos: 
    :language: C
    :lines: 22-41

Read the SW signal pin of the rotary encoder, and determine whether the rotary encoder is pressed. If it is pressed, the variable previousCounterValue is cleared.

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/31.2.1_Dimmable/Dimmable.c
    :linenos: 
    :language: C
    :lines: 54-59

The variable previousCounterValue is limited here, and the PWM duty cycle of ledPin is set to previousCounterValue. The duty cycle of PWM should be less than or equal to 100.

.. code-block:: c

    if(previousCounterValue>=100){
            previousCounterValue=100;
    }
    if(previousCounterValue<=0){
        previousCounterValue=0; 
    }
    softPwmWrite(ledPin,previousCounterValue);    //Mapping to PWM duty cycle