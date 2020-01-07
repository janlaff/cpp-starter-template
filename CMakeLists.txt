cmake_minimum_required(VERSION 3.15)

include(cmake/HunterGate.cmake)
HunterGate(
        URL "https://github.com/ruslo/hunter/archive/v0.23.214.tar.gz"
        SHA1 "e14bc153a7f16d6a5eeec845fb0283c8fad8c358"
)

# Set c++ version here
set(CMAKE_CXX_STANDARD 20)

# Set project name here
project(cpp_starter_template)

# Hunter Packages
hunter_add_package(Catch)

# Cmake Libraries
find_package(Catch2 CONFIG REQUIRED)

# Libraries to link
set(
		LIBRARIES
		# Native libraries
		pthread
		# Hunter exported library targets

)

file(
        GLOB
		SOURCE_FILES
		list(FILTER src/*.cpp EXCLUDE src/main.cpp)
)

add_library(${CMAKE_PROJECT_NAME}-lib STATIC ${SOURCE_FILES})
target_include_directories(${CMAKE_PROJECT_NAME}-lib PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)
target_link_libraries(${CMAKE_PROJECT_NAME}-lib PUBLIC ${LIBRARIES})

add_executable(${CMAKE_PROJECT_NAME} src/main.cpp)
target_link_libraries(${CMAKE_PROJECT_NAME} PUBLIC ${CMAKE_PROJECT_NAME}-lib)

# Tests
add_subdirectory(test)