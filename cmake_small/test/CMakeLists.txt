# Top level tests
cmake_minimum_required(VERSION 3.0.0)

set( TEST_PROJECT_NAME MainTests )
set( PROJECT_TESTS_SOURCE MainTests.cpp )

project( ${TEST_PROJECT_NAME} )

enable_testing()

add_executable( ${TEST_PROJECT_NAME} ${PROJECT_TESTS_SOURCE} )
# target_link_libraries( ${TEST_PROJECT_NAME} 
#                        gtest 
#                        gtest_main 
#                        ${PROJECT_EXT_LIBS} # NOTE: This is defined from project above
                    #  )

# if using catch + fakeit instead of googletest
target_link_libraries( ${TEST_PROJECT_NAME}
                       ${PROJECT_EXT_LIBS}
                     )

add_test( ${TEST_PROJECT_NAME} ${TEST_PROJECT_NAME} )
