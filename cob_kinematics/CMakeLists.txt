cmake_minimum_required(VERSION 2.8.3)
project(cob_kinematics)

find_package(catkin REQUIRED COMPONENTS geometry_msgs message_generation moveit_core moveit_msgs pluginlib roscpp std_msgs tf_conversions urdf)

add_service_files(
  FILES
  GetPositionIKExtended.srv
)

generate_messages(
  DEPENDENCIES geometry_msgs moveit_msgs std_msgs
)

catkin_package(
  CATKIN_DEPENDS geometry_msgs message_runtime moveit_msgs std_msgs
)

### BUILD ###
include_directories( ${catkin_INCLUDE_DIRS})

#add_executable(urdf_openrave ros/src/urdf_openrave.cpp)
add_subdirectory(ikfast)

### INSTALL ###
