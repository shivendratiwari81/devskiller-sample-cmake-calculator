cmake_minimum_required(VERSION 3.0)
project(cpp_calc)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

aux_source_directory(src SOURCE_FILES)
aux_source_directory(test TEST_SOURCE_FILES)

enable_testing()
find_package(GTest REQUIRED)
include_directories(${GTEST_INCLUDE_DIRS})

add_executable(testing ${SOURCE_FILES} ${TEST_SOURCE_FILES})
target_link_libraries(testing ${GTEST_BOTH_LIBRARIES})

add_test(AllTests testing)