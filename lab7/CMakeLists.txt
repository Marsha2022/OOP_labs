cmake_minimum_required(VERSION 3.10)
project(lab7)
 
enable_testing()

set(SOURCES src/npc.cpp src/princess.cpp src/knight.cpp src/dragon.cpp)

add_executable(lab7 main.cpp ${SOURCES})
target_include_directories(lab7 PRIVATE include)
set_target_properties(lab7 PROPERTIES OUTPUT_NAME "main")
 
add_executable(lab7_tests tests.cpp ${SOURCES})
target_include_directories(lab7_tests PRIVATE include)
set_target_properties(lab7_tests PROPERTIES OUTPUT_NAME "tests")
 
target_link_libraries(
  lab7_tests
  GTest::gtest_main
)
 
include(GoogleTest)
gtest_discover_tests(lab7_tests)
