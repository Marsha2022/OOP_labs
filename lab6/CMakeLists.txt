cmake_minimum_required(VERSION 3.10)
project(lab6)
 
enable_testing()

set(SOURCES src/observer.cpp src/princess.cpp src/dragon.cpp src/knight.cpp src/npc.cpp)

add_executable(lab6 main.cpp ${SOURCES})
target_include_directories(lab6 PRIVATE include)
set_target_properties(lab6 PROPERTIES OUTPUT_NAME "main")
 
add_executable(lab6_tests tests.cpp ${SOURCES})
target_include_directories(lab6_tests PRIVATE include)
set_target_properties(lab6_tests PROPERTIES OUTPUT_NAME "tests")
 
target_link_libraries(
  lab6_tests
  GTest::gtest_main
)
 
include(GoogleTest)
gtest_discover_tests(lab6_tests)
