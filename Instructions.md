The goal of this repository is to adapt the Dilithium Power Systems' Photon1 configuration tool to use the CAN Adapter we have made by Ewert Energy Systems.  
Helpful Links:
* https://www.ewertenergy.com/products.php?item=candapter&page=samplecode
* https://github.com/dilithiumpower/mppt_config/tree/master/util
Using the Java Example code (You can also refer to the rough Python implimentation [here](https://github.com/Solar-Gators/emulators/blob/master/CANAdapter/CANAdapter.py) we need to recreate the [CAN Ethernet](https://github.com/dilithiumpower/mppt_config/blob/master/util/can_ethernet.py) python module.  
This tool provided by the Dilithium guys was intended to utilize the [Tritium CAN to Ethernet bridge](https://tritiumcharging.com/product/solar-racing/) which we do not have in order to configfure the MPPTs. Since we have a CAN to USB bridge we should be able to just replace the CAN Ethernet Driver with a custom CAN USB driver.

Testing:
* Hook MPPT up to 12v
* Attach CAN Adapter to CAN High and CAN Low
* Read current MPPT configuration
* Modify output voltage to 108 volts
* Read back modified voltage

Notes:
The MPPT config tool uses protobuf you'll need that to run the python file.

Warning:
* We need to be fairly sure this works properly before testing on the MPPTs we can use old boards (like telemetry) to ensure the expected CAN Messages are being sent.

Other Options:
Create a util from scratch in your choice of language. This would be qute a lot of work thats why I have suyggested the above approach.

Good Luck!
