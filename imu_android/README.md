# imu_android

-----

## Usage

* start **Wireless IMU** Android apk, you can download it from [here](https://download.csdn.net/download/u011178262/12406719)

<p align="center">
  <img src="images/wimu_app.jpg"/>
</p>

* `python scripts/imu_data_raw.py` or `rosrun imu_android imu_data_raw.py`

<p align="center">
  <img src="images/wimu_client.jpg"/>
</p>

* if you want to publish `sensor_msgs/Imu` topic, replace `imu_data_raw.py` with `imu_data.py`