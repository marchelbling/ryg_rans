project(rans)
cmake_minimum_required(VERSION 3.2)

if(NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE "Release")
endif()


add_executable(rans main.cpp platform.h rans_byte.h)
add_executable(rans_64 main64.cpp platform.h rans64.h)
add_executable(rans_alias main_alias.cpp platform.h rans_byte.h)

set (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -msse4.1")
add_executable(rans_sse41 main_simd.cpp platform.h rans_word_sse41.h)
