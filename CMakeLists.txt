cmake_minimum_required(VERSION 3.5)
project(nmea_navsat_driver)

find_package(ament_cmake REQUIRED)
find_package(ament_cmake_python REQUIRED)

ament_python_install_package(
  libnmea_navsat_driver
  PACKAGE_DIR src/libnmea_navsat_driver
)

install(PROGRAMS
  nodes/nmea_serial_driver.py
  nodes/nmea_socket_driver.py
  nodes/nmea_tcpclient_driver.py
  nodes/nmea_topic_driver.py
  nodes/nmea_topic_serial_reader.py
  DESTINATION lib/${PROJECT_NAME}
)

install(DIRECTORY
  config
  launch
  DESTINATION share/${PROJECT_NAME}
)

ament_package()
