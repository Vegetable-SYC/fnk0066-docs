################################################################
Chapter Rotary Encoder
################################################################

.. include:: ../common/com.Rotary Encoder_1.rst

Code
================================================================

Python Code 31.1.1 RotaryEncoder
----------------------------------------------------------------

First observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:`  support@freenove.com

1.  Use ``cd`` command to enter 31.1.1_RotaryEncoder directory of Python code.

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/Python_GPIOZero_Code/31.1.1_RotaryEncoder

2.  Use python command to execute code ``RotaryEncoder.py``

.. code-block:: console

    $ python  RotaryEncoder.py

After the program is executed, the rotary encoder can count the number of output pulses during the forward and reverse rotation. When the rotary encoder is rotated clockwise by hand, the count value will increase. When the rotary encoder is rotated counterclockwise by hand , the count value will decrease. When the rotary encoder is pressed by hand, it can be reset to the initial state, that is, the count starts from 0.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/31.1.1_RotaryEncoder/RotaryEncoder.py
    :linenos: 
    :language: python

Function rotaryDeal() is used to determine whether the rotary encoder is rotating, and when there is rotation, determine whether it is rotating clockwise or counterclockwise. Use variable previousCounterValue to record the number of rotations. When rotating clockwise, the variable increases, and when rotating counterclockwise, the variable decreases.

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/31.1.1_RotaryEncoder/RotaryEncoder.py
    :linenos: 
    :language: python
    :lines: 24-38

sw.when_pressed associates the SW signal pin of the rotary encoder with sensorEvent(). When swPin detects a low level signal, the sensorEvent() function is called and executed. That is, each time the rotary encoder is pressed, the variable previousCounterValue is cleared.

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/31.1.1_RotaryEncoder/RotaryEncoder.py
    :linenos: 
    :language: python
    :lines: 40-47


.. include:: ../common/com.Rotary Encoder_2.rst

Code
================================================================

Python Code 31.2.1 Dimmable
----------------------------------------------------------------

First observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:`  support@freenove.com

1.  Use ``cd`` command to enter 31.2.1_Dimmable directory of Python code

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/Python_GPIOZero_Code/31.2.1_Dimmable

2.  Use python command to execute code ``Dimmable.py``

.. code-block:: console

    $ python Dimmable.py

After the program is executed, the rotary encoder can count the number of output pulses during forward and reverse rotation. Adjust the LED to emit different brightness by the number of rotations. When the rotary encoder is rotated clockwise by hand, the brightness of the led will increase, when the rotary encoder is rotated counterclockwise by hand, the brightness of the led will decrease, and when the rotary encoder is pressed by hand, the led will turn off.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/31.2.1_Dimmable/Dimmable.py
    :linenos: 
    :language: python

Function rotaryDeal() is used to determine whether the rotary encoder is rotating, and when there is rotation, determined whether it is rotating clockwise or counterclockwise. Use variable previousCounterValue to record the number of rotations. When rotating clockwise, the variable increases, and when rotating counterclockwise, the variable decreases.

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/31.2.1_Dimmable/Dimmable.py
    :linenos: 
    :language: python
    :lines: 25-39

sw.when_pressed associates the SW signal pin of the rotary encoder with sensorEvent(). When swPin detects a low level signal, the sensorEvent() function is called and executed. That is, each time the rotary encoder is pressed, the variable previousCounterValue is cleared.

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/31.2.1_Dimmable/Dimmable.py
    :linenos: 
    :language: python
    :lines: 41-48

The variable previousCounterValue is limited here, and the PWM duty cycle of ledPin is set to previousCounterValue. The duty cycle of PWM should be less than or equal to 100.

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/31.2.1_Dimmable/Dimmable.py
    :linenos: 
    :language: python
    :lines: 51-58
