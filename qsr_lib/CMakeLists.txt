cmake_minimum_required(VERSION 2.8.3)
project(qsr_lib)

find_package(catkin REQUIRED COMPONENTS
  rospy
  std_msgs
  message_generation
)

catkin_python_setup()

add_service_files(
  FILES
  RequestQSRs.srv
)

generate_messages(
  DEPENDENCIES
  std_msgs
)

catkin_package()

#############
## Install ##
#############

install(PROGRAMS
  scripts/example_ros_client.py
  scripts/example_standalone
  scripts/qsrlib_ros_server.py
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

install(DIRECTORY share
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
