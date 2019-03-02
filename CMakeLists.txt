cmake_minimum_required(VERSION 3.12)

list(APPEND CMAKE_MODULE_PATH ${CMAKE_BINARY_DIR})

option(ENABLE_COVERAGE "Enables generation of code coverage data if supported." OFF)
option(ENABLE_TESTS "Enables generation of code coverage data if supported." ON)

add_subdirectory(support)

if(ENABLE_TESTS)
    enable_testing()
    add_subdirectory(test)
endif()
