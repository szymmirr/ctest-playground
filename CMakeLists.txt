project(project)
cmake_minimum_required(VERSION 2.8)

add_executable(hello hello.cpp)

enable_testing()

add_test(hello_test hello)
set_tests_properties(hello_test PROPERTIES WILL_FAIL FALSE)
