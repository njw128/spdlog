cmake_minimum_required(VERSION 3.10)
project(spd_new)

set(CMAKE_CXX_STANDARD 11)
#INCLUDE_DIRECTORIES(include
#        ${CMAKE_CURRENT_SOURCE_DIR}/spdlog)
link_directories(${CMAKE_CURRENT_SOURCE_DIR}/spdlog)

find_package(Threads REQUIRED)

add_executable(spd_new main.cpp)
target_link_libraries(spd_new spdlog Threads::Threads)
target_include_directories(spd_new PUBLIC
        ${CMAKE_SOURCE_DIR})
file(MAKE_DIRECTORY "${CMAKE_CURRENT_BINARY_DIR}/logs")