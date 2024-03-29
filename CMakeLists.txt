cmake_minimum_required(VERSION 2.8.3)
project(assembly_msgs)

find_package(catkin REQUIRED COMPONENTS
  message_generation
  geometry_msgs
  sensor_msgs
  std_msgs
  actionlib_msgs
  actionlib
  vision_msgs
  darknet_ros_msgs
)

find_package(Eigen3 REQUIRED)

add_message_files(
  FILES
  simple.msg
)

add_action_files(DIRECTORY action FILES 
  AssembleApproach.action
  AssembleApproachBolt.action
  AssembleApproachHip.action
  AssembleExertForce.action
  AssembleSpiral.action
  AssembleVerifyCompletion.action	
  AssembleParallel.action
  AssembleMove.action
  AssembleSideChair.action
  AssembleRotation.action
  AssembleTripleRecovery.action
  AssembleDualArmSpiral.action
  AssembleDualArmApproach.action
  AssembleDualArmSideChairRecovery.action
  AssembleProbeEdge.action
  AssembleTripleMove.action
  AssembleRetreatBolt.action
  AssembleKitting.action
  AssembleBackForth.action
  TaskSpaceMove.action
  TaskSpaceMultipleMove.action
  AssembleBoltingReady.action
  AssembleTripleHold.action
  JointLimitAvoidance.action
  AssembleGMMDualArmSpiral.action
)

add_service_files(
  FILES
  IdleControl.srv
  ObjectConnection.srv
  SetTrajectoryFollowerGain.srv
  GetObjectPoseArray.srv
  GetObjectPose.srv
  GetObjectPose_with_points.srv
  SetSpiralGain.srv
  GetOccupancyVoxel.srv
)

generate_messages(
  DEPENDENCIES std_msgs geometry_msgs actionlib_msgs vision_msgs sensor_msgs
)

catkin_package(
  CATKIN_DEPENDS message_runtime std_msgs
  geometry_msgs
  sensor_msgs
  vision_msgs
)

include_directories(
  ${catkin_INCLUDE_DIRS}
)
