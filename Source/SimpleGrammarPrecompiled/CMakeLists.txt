cmake_minimum_required(VERSION 3.5)

project(SimpleGrammarPrecompiled)

add_executable (SimpleGrammarPrecompiled SimpleGrammarPrecompiled.cpp)

target_link_libraries(SimpleGrammarPrecompiled 
    SimpleGrammarLib
)

add_test(
    NAME GermanGLRTest 
    COMMAND SimpleGrammarPrecompiled --language German --input ${PROJECT_SOURCE_DIR}/tests/test.grm --output tests/out.txt
    WORKING_DIRECTORY  ${PROJECT_SOURCE_DIR}

)

add_test(
    NAME GermanGLRTestCompare 
    COMMAND ${CMAKE_COMMAND} -E compare_files ${PROJECT_SOURCE_DIR}/tests/canon.log tests/out.txt
    WORKING_DIRECTORY  ${PROJECT_SOURCE_DIR}

)

