cmake_minimum_required(VERSION 3.1)
project(SalientPoses)

# Set up the build environment's variables
set(PROJECT_PATH ${CMAKE_CURRENT_BINARY_DIR}/${PROJECT})
set(CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cgcmake/modules)

# Add the OpenCL and Maya libraries
find_package(Maya REQUIRED)

# Set the install prefix based on Maya
set(CMAKE_INSTALL_PREFIX ${CMAKE_CURRENT_BINARY_DIR})

# Add our project setup and meta-data
add_subdirectory(src)
configure_file("${CMAKE_CURRENT_SOURCE_DIR}/module.txt" "${PROJECT_PATH}/${PROJECT_NAME}.txt")
