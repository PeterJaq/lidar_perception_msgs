cmake_minimum_required(VERSION 2.8.3)

project(lidar_perception_msgs)

set(CMAKE_CXX_FLAGS "-std=c++11 ${CMAKE_CXX_FLAGS}")

find_package(catkin REQUIRED
  COMPONENTS
    actionlib_msgs
    geometry_msgs
    sensor_msgs
    std_msgs
    message_generation
)

add_message_files(
  FILES
    BoundingBox3D.msg
    BoundingBoxes3D.msg
    ObjectCount.msg
    DetPerf.msg
)

# add_action_files(
#   FILES
#     CheckForObjects.action
# )

generate_messages(
  DEPENDENCIES
    actionlib_msgs
    geometry_msgs
    sensor_msgs
    std_msgs
)

catkin_package(
  CATKIN_DEPENDS
    actionlib_msgs
    geometry_msgs
    sensor_msgs
    message_runtime
    std_msgs
)