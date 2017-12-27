cmake_minimum_required(VERSION 2.8.4)

set(LZ4_LIBRARY_DIR "" CACHE STRING "Path to the lz4 library directory.")

set(CMAKE_POSITION_INDEPENDENT_CODE ON)

if(NOT "${LZ4_LIBRARY_DIR}" EQUAL "")
  link_directories(${LZ4_LIBRARY_DIR})
endif()

add_library(lz4_stream STATIC lz4_input_stream.cpp lz4_output_stream.cpp)

target_link_libraries(lz4_stream lz4)
