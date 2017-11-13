cmake_minimum_required(VERSION 3.1)
project(xtensor-example)

find_package(xtensor REQUIRED CONFIG)
# ideally, should be included in the xtensor's cmake target
find_package(xtl REQUIRED CONFIG)
find_package(xsimd CONFIG)
#find_package(Threads)

# enforce C++14
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_CXX_STANDARD 14)

add_executable(
    example
    example.cpp
)

target_include_directories(
    example
    PRIVATE
    ${xsimd_INCLUDE_DIRS}
    ${xtl_INCLUDE_DIRS}
    ${xtensor_INCLUDE_DIRS}
)

# all header-only
# target_add_libraries
