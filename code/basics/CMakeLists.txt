cmake_minimum_required(VERSION 2.8.3)
project(basics)

find_package(
  catkin REQUIRED COMPONENTS
  roscpp
  rospy
  std_msgs
  message_generation
  actionlib_msgs
)

add_message_files(
  FILES
  Complex.msg
)

add_service_files(
  FILES
  WordCount.srv
)

add_action_files(
  DIRECTORY action
  FILES Timer.action
)

generate_messages(
  DEPENDENCIES
  actionlib_msgs
  std_msgs
)

catkin_package(
  CATKIN_DEPENDS
  message_runtime
  actionlib_msgs
)
