# oomwoo-esp32s3-cm

Spec TBD; Not decided if we need this or not.

Pi CM4/CM5-compatible Compute Module using ESP32-S3 instead of CPU

Purpose - cost reduced "educational" version of OOMWOO open-source vacuum cleaner
robot by replacing Pi CM4/CM5 with ESP32-S3, moving mapping/navigation compute to
a separate local PC running ROS2.

Tradeoffs:
- this is not a "consumer product" anymore due to the need to set up the additional ROS2 local PC
- no camera-based obstacle recognition

- mounts on [OOMWOO carrier I/O board](https://github.com/makerspet/oomwoo-io-board)
- pin-compatible CM4/CM5 Compute Module using ESP32-S3 (instead of CPU)
- expose GPIOs on CM4/CM5 headers
  - 1x serial to MCU
  - GPIOs (MCU acts as watchdog for ESP32-S3, can reset it if ESP32-S3 is unresponsive)
  - SPI (to IMU on I/O board)
  - I2C
  - 1x serial to LiDAR (via I/O board)
- Problem - no cameras, ESP32-S3 supports DVP parallel only, not MIPI
