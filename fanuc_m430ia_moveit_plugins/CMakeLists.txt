cmake_minimum_required(VERSION 2.8.3)
project(fanuc_m430ia_moveit_plugins)

find_package(Eigen REQUIRED)
include_directories(SYSTEM ${EIGEN_INCLUDE_DIRS})

find_package(LAPACK REQUIRED)

find_package(catkin REQUIRED COMPONENTS
  moveit_core
  pluginlib
  roscpp
  tf_conversions
)

include_directories(${catkin_INCLUDE_DIRS})
link_directories(${catkin_LIBRARY_DIRS})

catkin_package(
  LIBRARIES
  DEPENDS
  moveit_core
  pluginlib
  roscpp
  tf_conversions
)

add_subdirectory(m430ia2p_kinematics)
