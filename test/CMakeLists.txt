cmake_minimum_required(VERSION 3.15)

file(
        GLOB
        TEST_FILES
        *.cpp
)

add_executable(${CMAKE_PROJECT_NAME}-test ${TEST_FILES})
target_link_libraries(${CMAKE_PROJECT_NAME}-test PUBLIC Catch2::Catch2 ${CMAKE_PROJECT_NAME}-lib)