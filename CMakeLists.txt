cmake_minimum_required(VERSION 3.13)

set(CMAKE_CXX_STANDARD 14)

if (CMAKE_COMPILER_IS_GNUCC)
    option(ENABLE_COVERAGE "Enable coverage reporting for gcc/clang" FALSE)
    if (ENABLE_COVERAGE)
        add_compile_options(--coverage -O0 -fprofile-arcs -ftest-coverage)
        add_link_options(-coverage -lgcov)
    endif()
endif()

if (MSVC)
    add_compile_options(/W4)
else()
    add_compile_options(-Wall -Wextra -Wpedantic)
endif()

add_executable(starter main.cpp)

enable_testing()
add_executable(tester test.cpp)
target_link_libraries(tester --coverage)
add_test(Tester tester)
