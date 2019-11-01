cmake_minimum_required(VERSION 2.8.3)
project(assembly_msgs)

find_package(catkin REQUIRED COMPONENTS
  message_generation
  geometry_msgs
  sensor_msgs
  std_msgs
  actionlib_msgs
  actionlib
)


add_message_files(
  FILES
  simple.msg
)

add_action_files(DIRECTORY action FILES 
  AssembleApproach.action
  AssembleExertForce.action
  AssembleSpiral.action
  AssembleVerifyCompletion.action	
  AssembleParallel.action
  AssembleMove.action
  AssembleSideChair.action
)

add_service_files(
  FILES
  IdleControl.srv
)

generate_messages(
  DEPENDENCIES std_msgs geometry_msgs actionlib_msgs
)

catkin_package(
  CATKIN_DEPENDS message_runtime std_msgs
  geometry_msgs
  sensor_msgs
)

include_directories(
  ${catkin_INCLUDE_DIRS}
)
