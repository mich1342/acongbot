cmake_minimum_required(VERSION 3.8)
project(acongbot_gazebo)


find_package(ament_cmake REQUIRED)
find_package(ament_cmake_python REQUIRED)
find_package(rclpy REQUIRED)
ament_python_install_package(scripts)

install(
  DIRECTORY launch rviz worlds
  DESTINATION share/${PROJECT_NAME}
)

install(PROGRAMS
  scripts/command_timeout.py
  DESTINATION lib/${PROJECT_NAME}
)

ament_package()
