##############################################################################
Chapter High-sensitivity microphone sensor
##############################################################################

.. include:: ../common/com.High-sensitivity microphone sensor.rst

Code
================================================================

First observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:` support@freenove.com

1.  Use ``cd`` command to enter 26.1.1_VoiceLamp directory of C code.

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/C_Code/26.1.1_VoiceLamp

2.  Use following command to compile ``VoiceLamp.c`` and generate executable file ``VoiceLamp``.

.. code-block:: console

    $ gcc VoiceLamp.c -o VoiceLamp -lwiringPi

3.  Run the generated file ``VoiceLamp``

.. code-block:: console

    $ sudo ./VoiceLamp

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/26.1.1_VoiceLamp/VoiceLamp.c
    :linenos: 
    :language: C

Read the signal pin of the high-sensitivity microphone sensor, and determine whether the state of the sensor is high level. If it is high level, the LED will continue to turn on for 5 seconds.

.. code-block:: c

    if(digitalRead(sensorPin) == LOW){    //The sensor is blocked 
        digitalWrite(ledPin, HIGH);       //Make GPIO output HIGH level
        delay(5000);
        digitalWrite(ledPin, LOW);
        printf("led turned on >>>\n");    //Output information on terminal
    }
    else{                                //The sensor is not blocked
        digitalWrite(ledPin, LOW);       //Make GPIO output LOW level
        printf("led turned off <<<\n");  //Output information on terminal
    }