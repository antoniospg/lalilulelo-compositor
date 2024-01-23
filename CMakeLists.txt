cmake_minimum_required(VERSION 3.21)
project(lalilulelo)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include(FindPkgConfig)
pkg_check_modules(MIRAL miral REQUIRED)

add_executable(lalilulelo main.cpp)

target_include_directories(lalilulelo PUBLIC SYSTEM ${MIRAL_INCLUDE_DIRS})
target_link_libraries(     lalilulelo               ${MIRAL_LDFLAGS})
