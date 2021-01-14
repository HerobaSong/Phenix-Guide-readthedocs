Quick Connections
===================================

.. image:: /images/Quick_Connections.png
   :alt: Quick Connections
   :Width: 100%

System settings in the function is still perfect, can only use the modified mac address.  
**STEP 1** Connect RobSense Phenix Pro's Serial1 port with SwarmLink node UART port.  
**STEP 2** Connect SwarmLink Gateway micro USB with ground station.  
**STEP 3** Select the ground station serial number, baud rate, click open serial port.

Hardware parameters
-------------------

| CPU：ARM Cortex-M3
| Working frequency：433MHz
| Channel bandwidth：500KHz
| Modulation mode：LoRa spread spectrum
| Transmit power：20dBm
| Receiving sensitivity : -148dBm
| Working voltage：5V
| Working current：50mA
| Working temperature：-40℃-+85℃
| Interface：CAN，MicroUSB，LAN
| Size：60mm_37mm_11mm
| Weight：20g

.. image:: /images/Hardware\ parameters.png
   :Width: 50%

SwarmLink Node/Gateway：1.TXD 2.RXD 3.VCC 4.GND

Flight Controller Configuration (PX4 1.7.3)
-------------------------------------------

If the developer is using px4-1.7.3 version, there is need to modify original firmware. The red boxes below show the code to be modified or added.  
**Mavlink update:**  

.. figure:: /images/Mavlink\ update01.png
   :Width: 100%

.. figure:: /images/Mavlink\ update02.png
   :Width: 100%

1. Find the firmware/SRC/module/mavlink/mavlink\_main.cpp file.  
2. Add code in the corresponding position, as shown in the 1, 2, 3, 4 and 5 steps shown above.

**Turn off serial port flow control:** 

.. figure:: /images/Turn\ off\ serial\ port.png
   :Width: 100%

1. Find the firmware/SRC/module/mavlink/mavlink\_main.h file.  
2. Add code in the corresponding position, as shown in the 1 steps shown above.  
3. Find the firmware/SRC/module/mavlink/mavlink\_main.cpp file.  
4. Add code in the corresponding position, as shown in the 2,3,4 steps shown above.  

**Modify boot file:**  

.. figure:: /images/Modify\ boot\ file.png
   :Width: 100%

1. Find firmware/ROMFS/px4fmu\_common/init.d/rcS file.  
2. add the code at the corresponding location, as shown in the red area above.


