# Minimum CMake version
cmake_minimum_required(VERSION 3.10)

# Project name and settings
project(MyApp)

# Set C++ standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall")

# Directories for source and object files
set(SRC_DIR src)
set(OBJ_DIR ${CMAKE_BINARY_DIR}/obj)

# Gather all source files
file(GLOB SRC_FILES "${SRC_DIR}/*.cpp")

# Add executable target
add_executable(${PROJECT_NAME} ${SRC_FILES})

# Set output directories
set_target_properties(${PROJECT_NAME} PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/output
    ARCHIVE_OUTPUT_DIRECTORY ${OBJ_DIR}
    LIBRARY_OUTPUT_DIRECTORY ${OBJ_DIR}
    OUTPUT_NAME myapp
)
