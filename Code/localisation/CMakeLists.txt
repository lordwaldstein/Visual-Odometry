cmake_minimum_required(VERSION 2.8.3)
project(localisation)

find_package(catkin REQUIRED COMPONENTS
  cv_bridge
  image_transport
  roscpp
  sensor_msgs
  std_msgs
  geometry_msgs
)
 find_package(OpenCV REQUIRED)

catkin_package()


include_directories(
  ${catkin_INCLUDE_DIRS}
)
include_directories(${OpenCV_INCLUDE_DIRS})

add_executable(localisation src/main.cpp)
target_link_libraries(localisation ${catkin_LIBRARIES} )
 target_link_libraries(localisation ${OpenCV_LIBRARIES})
