cmake_minimum_required(VERSION 3.9)

set(CMAKE_CXX_STANDARD 14)

if (MSVC)
    add_compile_options(/W4)
else()
    add_compile_options(-Wall -Wextra -Wpedantic)
endif()

add_executable(starter main.cpp)

enable_testing()
add_executable(tester test.cpp)
add_test(Tester tester)