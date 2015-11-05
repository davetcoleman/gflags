cmake_minimum_required(VERSION 2.8.3)
project(gflags)

find_package(catkin)

# Gflags
set(CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)
find_package(Gflags REQUIRED)

include_directories(
  ${Gflags_INCLUDE_DIRS}
)

catkin_package(
  LIBRARIES
    gflags
)