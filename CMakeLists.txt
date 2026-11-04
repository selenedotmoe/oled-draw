cmake_minimum_required(VERSION 3.16)
project(main)

# set output directories
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/$<CONFIGURATION>")
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/$<CONFIGURATION>")

# include SDL source
add_subdirectory(vendored/SDL EXCLUDE_FROM_ALL)

# create executable
add_executable(main WIN32 main.c)

# link to SDL library
target_link_libraries(main PRIVATE SDL3::SDL3)
