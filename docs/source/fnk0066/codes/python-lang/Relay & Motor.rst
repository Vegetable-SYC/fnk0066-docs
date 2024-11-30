################################################################
Chapter Relay & Motor
################################################################

.. include:: ../common/com.Relay & Motor.rst

Code
================================================================

The project code is in the same as we used earlier in the Table Lamp project. Pressing the Push Button Switch activates the transistor. Because the Relay and the LED are connected in parallel, they will be powered ON at the same time. Press the Push Button Switch again will turn them both OFF.

Python Code 14.1.1 Relay
----------------------------------------------------------------

First, observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:`  support@freenove.com

1.	Use ``cd`` command to enter 14.1.1_Relay directory of Python code.

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/Python_GPIOZero_Code/14.1.1_Relay

2.	Use Python command to execute code ``Relay.py``. 

.. code-block:: console

    $ python Relay.py

After the program is executed, pressing the Push Button Switch activates the Relay (the internal switch is closed), which powers the DC Motor to rotate and simultaneously powers the LED to turn ON. If you press the Push Button Switch again, the Relay is deactivated (the internal switch opens), the Motor STOPS and the LED turns OFF.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/14.1.1_Relay/Relay.py
    :linenos: 
    :language: python

The project code is in the same as we used earlier in the Table Lamp project.