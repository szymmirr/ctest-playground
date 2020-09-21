project(project)
cmake_minimum_required(VERSION 2.8)

add_executable(test test.c)

add_executable(hello hello.cpp)

enable_testing()
add_test(usage_test test)
set_tests_properties(usage_test PROPERTIES WILL_FAIL TRUE)

add_test(success_test test 0)
set_tests_properties(success_test PROPERTIES PASS_REGULAR_EXPRESSION "SUCCESS")

add_test(fail_test test 1)
set_tests_properties(fail_test PROPERTIES WILL_FAIL TRUE)

add_test(fail_test_output test 1)
set_tests_properties(fail_test_output PROPERTIES PASS_REGULAR_EXPRESSION "FAIL")

add_test(hello_test hello)
set_tests_properties(hello_test PROPERTIES WILL_FAIL FALSE)

add_test(hello_test_output hello)
set_tests_properties(hello_test_output PROPERTIES PASS_REGULAR_EXPRESSION 8)

add_test(hello_test_output_fail hello)
set_tests_properties(hello_test_output_fail PROPERTIES PASS_REGULAR_EXPRESSION 9 WILL_FAIL)
