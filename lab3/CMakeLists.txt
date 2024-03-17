cmake_minimum_required(VERSION 3.10)
project(lab3)
 
enable_testing()

set(SOURCES src/Figure.cpp src/Trapezoid.cpp src/Rhombus.cpp src/Pentagon.cpp src/Array.cpp)

add_executable(lab3 main.cpp ${SOURCES})
target_include_directories(lab3 PRIVATE include)

set_target_properties(lab3 PROPERTIES OUTPUT_NAME "main")
 
add_executable(lab3_tests tests.cpp ${SOURCES})
target_include_directories(lab3_tests PRIVATE include)
set_target_properties(lab3_tests PROPERTIES OUTPUT_NAME "tests")
 
target_link_libraries(
  lab3_tests
  GTest::gtest_main
)
 
include(GoogleTest)
gtest_discover_tests(lab3_tests)
