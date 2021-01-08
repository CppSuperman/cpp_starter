cmake_minimum_required(VERSION 3.10)

set(CMAKE_CXX_STANDARD 14)

if (MSVC)
    add_compile_options(/W4)
else()
    add_compile_options(-Wall -Wextra -Wpedantic)
endif()

add_executable(starter main.cpp)