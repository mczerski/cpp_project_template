cmake_minimum_required(VERSION 2.8)
project (${TEMPLATE_PROJECT})

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

file(GLOB SRC ./src/*.cpp)
add_library(core STATIC ${SRC})

add_executable(${PROJECT_NAME} main.cpp)
target_link_libraries(${PROJECT_NAME} core)

enable_testing()
find_library(GMOCK gmock)
find_library(GMOCK_MAIN gmock_main)
file(GLOB TEST_SRC ./test/*.cpp)
add_executable(tests ${TEST_SRC})
target_link_libraries(tests core ${GMOCK} ${GMOCK_MAIN} pthread)

add_test(NAME Tests COMMAND tests)
