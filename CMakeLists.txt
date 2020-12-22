cmake_minimum_required(VERSION 2.8 FATAL_ERROR)
add_definitions(-std=c++11)

set(CXX_FLAGS "-wall" "-pedantic")
set(CMAKE_CXX_FLAGS, "${CXX_FLAGS}")
# set(OpenCV_DIR /usr/local/share/OpenCV)

project(camera_fusion)

find_package(OpenCV 4.1 REQUIRED)

include_directories(${OpenCV_INCLUDE_DIRS})
link_directories(${OpenCV_LIBRARY_DIRS})
add_definitions(${OpenCV_DEFINITIONS})

add_executable(detect_objects src/detect_objects_2.cpp)
target_link_libraries(detect_objects ${OpenCV_LIBRARIES})
