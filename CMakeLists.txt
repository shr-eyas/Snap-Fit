cmake_minimum_required(VERSION 3.10)

# Project name and version
project(Snap-Fit VERSION 1.0)

# Specify the C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Path to Dynamixel SDK (relative to project root)
set(DYNAMIXEL_SDK_DIR "${CMAKE_SOURCE_DIR}/DynamixelSDK")

# Include directories for Dynamixel SDK
include_directories(${DYNAMIXEL_SDK_DIR}/c++/include)

# Link directories for Dynamixel SDK
link_directories(${DYNAMIXEL_SDK_DIR}/c++/build/linux64)

# Add executable
add_executable(snap_fit src/main.cpp)

# Link the Dynamixel SDK shared library
target_link_libraries(snap_fit dxl_x64_cpp)
