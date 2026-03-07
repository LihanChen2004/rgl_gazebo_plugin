cmake_minimum_required(VERSION 3.21)
project(rgl_gazebo_plugin)


set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
if (CMAKE_INSTALL_PREFIX_INITIALIZED_TO_DEFAULT)
    set(CMAKE_INSTALL_PREFIX "${PROJECT_SOURCE_DIR}/install")
endif()

find_package(ament_cmake_auto)

add_subdirectory(external)
add_subdirectory(RGLServerPlugin)
add_subdirectory(RGLVisualize)
ament_environment_hooks("${CMAKE_CURRENT_SOURCE_DIR}/hooks/${PROJECT_NAME}.dsv.in")

ament_auto_package(
  INSTALL_TO_SHARE
  lidar_patterns
)
