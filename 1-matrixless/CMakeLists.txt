cmake_minimum_required(VERSION 3.1)
SET_PROPERTY(GLOBAL PROPERTY TARGET_SUPPORTS_SHARED_LIBS TRUE)
# Enable C++11

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED TRUE)
set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -Wall")
set(CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE} -Wall")

find_package( OpenCV REQUIRED )
include_directories( ${OpenCV_INCLUDE_DIRS} )


set(SRC "../lodepng/lodepng.h" "../lodepng/lodepng.cpp")
project(1-Matrixless)
add_executable(1-Matrixless ${SRC} "Fluid.cpp")

target_link_libraries( 1-Matrixless ${OpenCV_LIBS} )
