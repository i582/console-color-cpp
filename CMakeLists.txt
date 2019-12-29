cmake_minimum_required(VERSION 3.15)
project(console_color_cpp)

set(CMAKE_CXX_STANDARD 14)

include_directories(src)

add_executable(console_color_cpp
        src/console-color.hpp
        main.cpp)
