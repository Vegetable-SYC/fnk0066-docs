

In this chapter, we will learn how to use rotary encoder.

Project Rotary Encoder
****************************************************************

This project uses a rotary encoder to make a simple counter.

Component List
================================================================

+--------------------------------------------------+-------------------------------------------------+
|1. Raspberry Pi (with 40 GPIO) x1                 |                                                 |
|                                                  | Jumper Wires x7                                 |
|2. GPIO Extension Board & Ribbon Cable x1         |                                                 |
|                                                  |  |jumper-wire|                                  |
|3. Breadboard x1                                  |                                                 |
+--------------------------------------------------+-------------------------------------------------+
|Rotary encoder x1                                                                                   |
|                                                                                                    |
|  |Rotary_encoder|                                                                                  |
+----------------------------------------------------------------------------------------------------+

.. |jumper-wire| image:: ../_static/imgs/jumper-wire.png
.. |Rotary_encoder| image:: ../_static/imgs/Rotary_encoder.png
    :width: 40%

Component knowledge
================================================================

Rotary Encoder
----------------------------------------------------------------

A rotary encoder is a rotary sensor that converts the rotational displacement into a periodic electrical signal, and then converts the electrical signal into a count pulse, and uses the number of pulses to indicate the magnitude of the rotational displacement. It drives the internal grating disc to rotate through the rotation of the knob. Many slits are preset on the grating disc. The rotation of the grating disc causes the light passing through the slits to produce pulse changes. After the signal is processed by the subsequent circuit, it is output as a pulse signal. Finally, The rotary displacement of the knob can be obtained through the output of the signal pin. The encoder generates pulse signals through the configuration of the internal light source and photosensitive element. 

The working principle of the encoder and the schematic diagram of the output waveform are as follows:

.. image:: ../_static/imgs/Rotary_encoder_Knowledge.png
    :align: center

A rotary encoder gives two-phase square waves, which are 90° out of phase, commonly referred to as A channel and B channel. One of the channels gives the information related to the rotation speed. The information of the rotation direction is obtained by sequentially comparing the signals of the two channels. There is also a special signal called Z or zero channel, which gives the absolute zero position of the encoder. This signal is a square wave that coincides with the center line of the A channel square wave.
The following is the internal cross-sectional structure diagram of the encoder:

.. image:: ../_static/imgs/Rotary_encoder_Knowledge_1.png
    :align: center

The number of pulses per revolution of the rotary encoder in this project is 20. Its working voltage is 5V. The sensor has 5 pins: SW, CLK, DT, power supply positive pin and power supply negative pin. Among them, the SW pin is the input signal pin, the rotary encoder sensor itself is also a button, when the button is pressed, the SW pin will jump from high level to low level. The CLK pin is a rotation signal pin. When not rotating, this pin outputs a high level, and when rotating, it outputs a low level. The DT pin is used to determine the direction of rotation. If this pin is high when it is not rotating, and becomes low when it is rotating, it means that clockwise rotation has occurred. When this pin is high when it is rotating, it means that counterclockwise rotation has occurred. When the positive and negative pins of the module are connected to a suitable power supply, the module starts to work. At this time, three pins on the development board need to be used to read the SW, CLK and DT of the module respectively. Then according to the above principle, the state of the rotary encoder can be determine. 

For example, when you turn the encoder clockwise by hand, the CLK outputs low level, and the DT changes from high level to low level. When you rotate the encoder counterclockwise by hand, the CLK outputs low level, and the DT changes from low level to high level. When you press the rotary encoder by hand, the SW signal outputs low level.

Circuit
================================================================

+------------------------------------------------------------------------------------------------+
|   Schematic diagram                                                                            |
|                                                                                                |
|   |Rotary_encoder_Sc|                                                                          |
+------------------------------------------------------------------------------------------------+
|   Hardware connection. If you need any support,please feel free to contact us via:             |
|                                                                                                |
|   support@freenove.com                                                                         | 
|                                                                                                |
|   |Rotary_encoder_Fr|                                                                          |
+------------------------------------------------------------------------------------------------+

.. |Rotary_encoder_Sc| image:: ../_static/imgs/Rotary_encoder_Sc.png
.. |Rotary_encoder_Fr| image:: ../_static/imgs/Rotary_encoder_Fr.png