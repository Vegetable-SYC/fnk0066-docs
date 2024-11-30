################################################################
Chapter Speaker amplifier module PAM8403
################################################################

.. include:: ../common/com.Speaker amplifier module PAM8403_1.rst

Code
================================================================

Python Code 35.1.1 Music
----------------------------------------------------------------

Run program 

.. hint:: 
    :red:`If you have any concerns, please contact us via:`  support@freenove.com

1.  Use cd command to enter 35.1.1_Music directory of Python code.

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/Python_GPIOZero_Code/35.1.1_Music

2.  Use command to execute

.. code-block:: console

    $ ffplay test.mp3

After executing the command, you can hear the test music playing. Here you can also play other music in this way. You can exit playback by pressing Esc on the keyboard.

.. include:: ../common/com.Speaker amplifier module PAM8403_2.rst

Code
================================================================

Python Code 35.2.1 TTS
----------------------------------------------------------------

Install espeak before run python code.

1.  Enter the following command to install.

.. code-block:: console

    $ sudo apt-get install espeak

Enter 'y' to continu espeak library installation.

First observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:`  support@freenove.com

2.  Use cd command to enter 35.2.1_TTS directory of Python code.

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/Python_GPIOZero_Code/35.2.1_TTS
3.  Use python command to execute code "TTS.py"

.. code-block:: console

    $ python TTS.py

After the program is executed, when you touch the infrared detection sensor, the speaker will broadcast "Hello, please stay away".

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/35.2.1_TTS/TTS.py
    :linenos: 
    :language: python
