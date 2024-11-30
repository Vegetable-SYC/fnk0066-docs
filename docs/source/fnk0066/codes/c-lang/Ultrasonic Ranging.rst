##############################################################################
Chapter Ultrasonic Ranging
##############################################################################

.. include:: ../common/com.Ultrasonic Ranging.rst

Code
================================================================

C Code 23.1.1 SenseLED
----------------------------------------------------------------

First, observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:` support@freenove.com

1.	Use ``cd`` command to enter 24.1.1_UltrasonicRanging directory of C code.

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/C_Code/24.1.1_UltrasonicRanging

2.	Use following command to compile "UltrasonicRanging.c" and generate executable file ``UltrasonicRanging``. 

.. code-block:: console

    $ gcc UltrasonicRanging.c -o UltrasonicRanging -lwiringPi

3.	Then run the generated file ``UltrasonicRanging``.

.. code-block:: console

    $ sudo ./UltrasonicRanging

After the program is executed, aim the Ultrasonic Ranging Module's detectors (“eyes”) perpendicular to the surface of an object (try using your hand). The distance between the ultrasonic module and the object will be displayed in the terminal. As is shown below:

.. image:: ../_static/imgs/distance.png
    :align: center

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/24.1.1_UltrasonicRanging/UltrasonicRanging.c
    :linenos: 
    :language: C
    :lines: 7-42

First, define the pins and the maximum measurement distance.

.. code-block:: console

    #define trigPin 4
    #define echoPin 5
    #define MAX_DISTANCE 220        //define the maximum measured distance

If the module does not return high level, we cannot wait for this forever, so we need to calculate the time period for the maximum distance, that is, time Out. **timeOut= 2*MAX_DISTANCE/100/340*1000000**. The result of the constant part in this formula is approximately 58.8.

.. code-block:: console

    #define timeOut MAX_DISTANCE*60

Subfunction **getSonar()** function is used to start the Ultrasonic Module to begin measurements and return the measured distance in cm units. In this function, first let trigPin send 10us high level to start the Ultrasonic Module. Then use **pulseIn()** to read the Ultrasonic Module and return the duration time of high level. Finally, the measured distance according to the time is calculated.

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/24.1.1_UltrasonicRanging/UltrasonicRanging.c
    :linenos: 
    :language: C
    :lines: 17-26

Lastly, in the while loop of main function, get the measurement distance and display it continually.

.. literalinclude:: ../../../freenove_Kit/Code/C_Code/24.1.1_UltrasonicRanging/UltrasonicRanging.c
    :linenos: 
    :language: C
    :lines: 36-40

About function pulseIn():

.. c:function:: int pulseIn(int pin, int level, int timeout);

    Return the length of the pulse (in microseconds) or 0 if no pulse is completed before the timeout (unsigned long).

