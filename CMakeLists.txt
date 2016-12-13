cmake_minimum_required(VERSION 2.8)
project (OpenVR)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${OpenVR_SOURCE_DIR}/cmake")
set(ARCH "64" CACHE STRING
  "ARCH chosen by the user at CMake configure time")
set_property(CACHE ARCH PROPERTY STRINGS 32 64)

message(STATUS "Compilation for '${ARCH}' Bit")
add_definitions ("-DLINUX")
add_definitions ("-DLINUX64")
add_definitions ("-DPOSIX")

add_subdirectory (src)
add_subdirectory (samples/hellovr_opengl)
