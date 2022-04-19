Python Modules
==============

IMU
---

The LSM6DSOXTR sensor assets/LSM6DSOXTR-NANORP2040CONNECT.png

LSM6DSOXTR
^^^^^^^^^^

The LSM6DSOXTR from STM is an IMU (Inertial Measurement Unit) that features a 3D digital accelerometer and a 3D digital gyroscope. It features among many other things, a machine learning core, which is useful for any motion detection projects, such as free fall, step detector, step counter, pedometer.

LSM6DSOX Library
""""""""""""""""

To access the data from the LSM6DSOX module, we need to install the LSM6DSOX
https://github.com/arduino-libraries/Arduino_LSM6DSOX) library, which comes
with examples that can be used directly with the Nano RP2040 Connect. 

It can be installed directly from the library manager through the IDE of your choice.
To use it, we need to include at the top of the sketch::

#include <Arduino_LSM6DSOX.h>

And to initialize the library, we can use the following command inside `void setup()`::

  if (!IMU.begin()) {
    Serial.println("Failed to initialize IMU!");
    while (1);
  }


Accelerometer
"""""""""""""

The accelerometer data can be accessed through the following commands::

  float x, y, z;

  if (IMU.accelerationAvailable()) {
    IMU.readAcceleration(x, y, z);
  }

Gyroscope
"""""""""

The gyroscope data can be accessed through the following commands::

  float x, y, z;

  if (IMU.gyroscopeAvailable()) {
    IMU.readGyroscope(x, y, z);
  }

Tutorials
"""""""""

If you want to learn more on how to use the IMU, please check out the tutorial below:

* Accessing IMU data with Nano RP2040 Connect /tutorials/nano-rp2040-connect/rp2040-imu-basics
* Using the IMU Machine Learning Core Features /tutorials/nano-rp2040-connect/rp2040-imu-advanced