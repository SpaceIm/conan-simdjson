cmake_minimum_required(VERSION 3.1)
project(test_package)

set(CMAKE_VERBOSE_MAKEFILE TRUE)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup()

find_package(simdjson REQUIRED CONFIG)

add_executable(${PROJECT_NAME} test_package.cpp)
target_link_libraries(${PROJECT_NAME} simdjson::simdjson)
set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD 11)
