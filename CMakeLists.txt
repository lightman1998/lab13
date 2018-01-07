cmake_minimum_required(VERSION 3.2.2)

set(CMAKE_CXX_COMPILER "g++")
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include(cmake/HunterGate.cmake)

HunterGate(
    URL "https://github.com/lightman1998/hunter/archive/v0.19.137.1.tar.gz"
    SHA1 "a7d84022ffa743c3a3647ce4841a42f00f11a8ad"
    LOCAL
)

project(pack)
hunter_add_package(yaml-cpp)
find_package(yaml-cpp CONFIG REQUIRED)

add_executable(pack ${CMAKE_CURRENT_SOURCE_DIR}/sources/pack.cpp)
target_link_libraries(pack yaml-cpp::yaml-cpp)
add_executable(unpack ${CMAKE_CURRENT_SOURCE_DIR}/sources/unpack.cpp)
target_link_libraries(unpack yaml-cpp::yaml-cpp)
