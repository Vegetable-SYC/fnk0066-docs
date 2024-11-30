################################################################
Chapter LEDpixel
################################################################

.. include:: ../common/com.LEDpixel_1.rst

Code
================================================================

Python Code 32.1.1 Ledpixel
----------------------------------------------------------------

Before running python code, please install WS281X library first.

1.	Enter the following command to install.

.. code-block:: console

    $ sudo pip3 install rpi_ws281x

The installation is completed as shown in the figure below.

.. image:: ../_static/imgs/rpi_ws281x.png
    :align: center

First observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:`  support@freenove.com

1.	Use ``cd`` command to enter 32.1.1_Ledpixel directory of Python code.

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/Python_GPIOZero_Code/32.1.1_Ledpixel

2.	Use python command to execute code ``Ledpixel.py``.

.. code-block:: console

    $ sudo python Ledpixel.py

After the program runs, the LEDpixel will emit red, green and blue colors in turn like flowing water. If your Freenove 8 RGB LED Module doesn't work, you can try :ref:`additional supplements` to solve.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/32.1.1_Ledpixel/Ledpixel.py
    :linenos: 
    :language: python

Import rpi_ws281x modile. Set the number, pins and brightness of the LED.

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/32.1.1_Ledpixel/Ledpixel.py
    :linenos: 
    :language: python
    :lines: 10-18

Define LED class.

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/32.1.1_Ledpixel/Ledpixel.py
    :linenos: 
    :language: python
    :lines: 20-29

Light up the eight LEDs in red, green and blue in turn.

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/32.1.1_Ledpixel/Ledpixel.py
    :linenos: 
    :language: python
    :lines: 34-45


.. include:: ../common/com.LEDpixel_2.rst

Code
================================================================

In this project, we will make a Servo rotate from 0 degrees to 180 degrees and then reverse the direction to make it rotate from 180 degrees to 0 degrees and repeat these actions in an endless loop.

Python Code 32.2.1 RainbowLight
----------------------------------------------------------------

If you did not configure I2C, please refer to :doc:`Chapter 7 ADC <ADC>`. If you did, please continue.

For Python code, ADCDevice requires a custom module which needs to be installed. If you have installed it in Chapter 7.Please skip the installation.

1.  Use ``cd`` command to enter folder of ADCDevice.

.. code-block:: console

    $ cd ~/Freenove_Kit/Libs/Python-Libs/

2.  Open the unzipped folder.

.. code-block:: console

    $ cd ADCDevice-1.0.4

3.  Install library for python2 and python3.

.. code-block:: console

    $ sudo python2 setup.py install 
    $ sudo python3 setup.py install 

First observe the project result, and then learn about the code in detail.

.. hint:: 
    :red:`If you have any concerns, please contact us via:`  support@freenove.com

4.  Use ``cd`` command to enter 32.2.1_Rainbow Light directory of Python code.

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/Python_GPIOZero_Code/32.2.1_RainbowLight

5.  Use python command to execute code ``RainbowLight.py``.

.. code-block:: console

    $ sudo python RainbowLight.py

After running the program, you can change the color of the LED module by rotating the potentiometer.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/32.2.1_RainbowLight/RainbowLight.py
    :linenos: 
    :language: python

This function converts HSL colors to RGB colors.

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/32.2.1_RainbowLight/RainbowLight.py
    :linenos: 
    :language: python

Read the ADC value of channel 2 in an infinite loop. Let the color of the eight LEDs change according to the value of the ADC.

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/32.2.1_RainbowLight/RainbowLight.py
    :linenos: 
    :language: python

Finally, in the "while" loop of main function, we need to use two separate cycles to make servo rotate from 0 degrees to 180 degrees and then from 180 degrees to 0 degrees. 

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/32.2.1_RainbowLight/RainbowLight.py
    :linenos: 
    :language: python


.. include:: ../common/com.LEDpixel_3.rst

Code
================================================================

Python Code 32.3.1 Ledpixel
----------------------------------------------------------------

Before you run your python code, check that the spidev library exists.

Enter the following command to install.

.. code-block:: console

    $ pip list

The spidev is installed on Raspberry PI by default. As shown in the figure below.

.. image:: ../_static/imgs/pip_list.png
    :align: center

If your Raspberry PI system does not have this library, you can find **spidev-3.6.tar.gz** in **Freenove_Kit/Libs/Python-Libs**. 

Enter the following instructions to install spidev.

.. code-block:: console

    $ cd Freenove_Kit/Libs/Python-Libs
    $ tar -zxvf spidev-3.6.tar.gz
    $ cd spidev-3.6
    $ sudo python setup.py install

The installation is complete as shown in the following figure.

.. image:: ../_static/imgs/installation.png
    :align: center

.. hint:: 
    :red:`If you have any concerns, please contact us via:`  support@freenove.com

Additional supplement 
================================================================

Note that the frequency of the SPI changes as the CPU frequency self-regulates, so we need to fix the cpu frequency before we start using the code. Please refer to the following operations.

1. Open the config.txt file and prepare to edit it.

.. code-block:: console

    $ sudo nano /boot/firmware/config.txt

2. If your Raspberry PI is Raspberry PI 4 or Raspberry PI 5, please add at the bottom:

.. code-block:: console

    $ force_turbo=1

If your Raspberry PI is Raspberry PI 3, add it at the bottom:

.. code-block:: console

    $ core_freq=250

3. Save the file.
4. Turn on the spi feature of the Raspberry PI.

.. code-block:: console

    $ sudo raspi-config

5. Select Interface Options, then SPI, and turn it on.

.. image:: ../_static/imgs/installation.png
    :align: center

6. Select Finish.

7. Reboot the Raspberry PI.

.. code-block:: console

    $ sudo reboot

Use cd command to enter 32.3.1_Ledpixel directory of Python code.

.. code-block:: console

    $ cd ~/Freenove_Kit/Code/Python_GPIOZero_Code/32.3.1_Ledpixel

Use python command to execute code "Ledpixel.py".

.. code-block:: console

    $ python Ledpixel.py

After the program runs, ledpixel emits red, green, and blue three colors in turn. And then the colors of the rainbow.

The following is the program code:

.. literalinclude:: ../../../freenove_Kit/Code/Python_GPIOZero_Code/32.3.1_Ledpixel/Ledpixel.py
    :linenos: 
    :language: python

Call the light library and the time library.

.. code-block:: python

    from SPI_Ledpixel import Freenove_SPI_LedPixel
    import time

Apply for a light object, set the number of lights to 8, brightness to 255, light type to "GRB", use the mosi pin of spi0 to control the lights.

.. code-block:: python

    # Freenove_SPI_LedPixel(led_count, led_brightness, led_transmission_sequence, spidev_bus)
    led = Freenove_SPI_LedPixel(8, 255, 'GRB', 0) 

Check whether the SPI is configured successfully.

.. code-block:: python

    if led.check_spi_state() != 0:

Reconfigure the number and brightness of ledpixel.

.. code-block:: python

    led.set_led_count(8)                     # Set the number of lights.
    led.set_led_brightness(20)                # Set the brightness of lights.

Let ledpixel display red, green and blue one by one, then turn off.

.. code-block:: python

    color = [[255,0,0],[0,255,0],[0,0,255],[0,0,0]]  # Set the color of the lights
    for j in range(4):
        for i in range(8):
            # Set the color of the lights, but it does not take effect
            led.set_led_rgb_data(i, color[j])        
            # Send the color data and make the color data effective
            led.show()
            time.sleep(0.1)

Let ledpixel cycle rainbow colors.

.. code-block:: python

    while True:
        for j in range(255):
            for i in range(led.led_count):
                #Converts values ranging from 0 to 255 to color data.
                led.set_led_rgb_data(i, led.wheel((round(i * 255 / led.led_count) + j)%256))
            led.show()
            time.sleep(0.002)

For more details, see Freenove_Kit/Code/Python_GPIOZero_Code/SPI_Ledpixel.py.
