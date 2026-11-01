cmake_minimum_required(VERSION 3.16)
project(hello)

# set output directories
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/$<CONFIGURATION>")
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/$<CONFIGURATION>")

# include SDL source
add_subdirectory(vendored/SDL EXCLUDE_FROM_ALL)

# create executable
add_executable(hello WIN32 hello.c)

# link to SDL library
target_link_libraries(hello PRIVATE SDL3::SDL3)
