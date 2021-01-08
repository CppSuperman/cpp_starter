cmake_minimum_required(VERSION 3.5)

if (MSVC)
    add_compile_options(/W4)
else()
    add_compile_options(-Wall -Wextra -Wpedantic)
endif()

add_executable(starter main.cpp)
target_compile_features(starter PRIVATE cxx_lambda_init_captures)