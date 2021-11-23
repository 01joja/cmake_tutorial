cmake_minimum_required(VERSION 3.10)

# This is only meant to get you started. 

# Set the project name and version.
project(Test VERSION 0.0.1)

# Set what c++ standard is used?
set(CMAKE_CXX_STANDARD 14)

# This adds the testfile so that CMake can find it.
add_subdirectory(test)

# This adds the C_sub to known folders and specifys where it should be saved in the build.
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/../C_sub ${CMAKE_CURRENT_BINARY_DIR}/C_sub)

# add the executable file
add_executable(Test main.cpp)

# ------------------------------------

# Adds the libary test from the test/CMakeLists.txt
target_link_libraries(Test PUBLIC test)

# Adds the libary test2 from the ../C_sub/CMakeLists.txt
target_link_libraries(Test PUBLIC test2)

# ------------------------------------

# Above is the same as below

# ------------------------------------

# You can add everything in one line like this:
target_link_libraries(Test PUBLIC test test2)

# ------------------------------------


