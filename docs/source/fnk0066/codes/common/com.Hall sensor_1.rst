

In this chapter, we will learn how to use Hall sensor.

Project Hall sensor and LED
****************************************************************

This project uses hall sensor to control the state of LED.

Component List
================================================================

+--------------------------------------------------+------------------------+
|1. Raspberry Pi (with 40 GPIO) x1                 |                        |     
|                                                  | Jumper Wires x6        |       
|2. GPIO Extension Board & Ribbon Cable x1         |                        |       
|                                                  |  |jumper-wire|         |                                                            
|3. Breadboard x1                                  |                        |                                                                 
+--------------------------------------------------+------------------------+
| Hall sensor x1                                   | LED x1                 |
|                                                  |                        |
|  |Hall_Sensor| :xx-large:`or` |Hall_Sensor_1|    |  |red-led|             |                           
+--------------------------------------------------+------------------------+
| Speaker x1                                       | Resistor 220Ω x1       |
|                                                  |                        |
|  |Speaker|                                       |  |res-220R|            |                           
+--------------------------------------------------+------------------------+

.. |jumper-wire| image:: ../_static/imgs/jumper-wire.png
.. |Hall_Sensor| image:: ../_static/imgs/Hall_Sensor.png
    :width: 30%
.. |Hall_Sensor_1| image:: ../_static/imgs/Hall_Sensor_1.png
    :width: 40%
.. |red-led| image:: ../_static/imgs/red-led.png
    :width: 20%
.. |res-220R| image:: ../_static/imgs/res-220R.png
    :width: 15%
.. |Speaker| image:: ../_static/imgs/Speaker.png
    :width: 40%

Component knowledge
================================================================

Hall sensor
----------------------------------------------------------------

Hall sensor is a magnetic field sensor made according to the Hall effect. Based on the Hall effect, Hall voltage varies with magnetic field strength. Hall sensors can be divided into linear (analog) Hall sensors and switching Hall sensors. Linear Hall sensors have two outputs: analog output (AO), digital output (DO). Switching Hall sensors only have digital output (DO) and the analog output (AO) output has no effect. In this project, the switch Hall sensor is used. Its use is very simple. 

This module has 4 pins: digital output (DO), analog output (AO), power supply positive pin and power supply negative pin. When the positive and negative pins of the module are connected to a suitable power supply, the module starts to work. Only one pin on the development board is needed to read the digital output (DO) signal of the module. In the project, the speaker is used as the magnetic field source, when you put the sensor close to the magnetic field (speaker), the DO outputs low level, and if the sensor does not sense the magnetic field (speaker), the DO outputs high level.

Below is the pinout of the Hall sensor.

**Pin description:**

.. list-table::
   :align: center
   :header-rows: 1
   :class: product-table

   * - symbol
     - Function

   * - VCC
     - Power supply pin, +3.3V~5.5V  

   * - DO
     - Output control signal

   * - AO
     - Output invalid

   * - GND
     - GND
    
Please do not use voltage beyond the power supply range to avoid damage to the Hall sensor.For the above two hall sensors, their difference is only the pin sequence is different, please get the Hall sensor, check its sequence, change the corresponding wiring, so as not to cause permanent damage to your raspberry PI.

Circuit
================================================================

+------------------------------------------------------------------------------------------------+
|   Schematic diagram                                                                            |
|                                                                                                |
|   |Hall_Sensor_Sc|                                                                             |
+------------------------------------------------------------------------------------------------+
|   Hardware connection. If you need any support,please feel free to contact us via:             |
|                                                                                                |
|   support@freenove.com                                                                         | 
|                                                                                                |
|   |Hall_Sensor_Fr| :xx-large:`or` |Hall_Sensor_Fr_1|                                           |
+------------------------------------------------------------------------------------------------+

.. |Hall_Sensor_Sc| image:: ../_static/imgs/Hall_Sensor_Sc.png
.. |Hall_Sensor_Fr| image:: ../_static/imgs/Hall_Sensor_Fr.png
    :width: 44%
.. |Hall_Sensor_Fr_1| image:: ../_static/imgs/Hall_Sensor_Fr_1.png
    :width: 48%

.. note::
    
    :red:`Please check the sequence of your Hall sensor and select the appropriate wiring to avoid permanent damage to your raspberry PI.`

