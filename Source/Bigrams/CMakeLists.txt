cmake_minimum_required(VERSION 3.5)

project(Bigrams)

add_executable (Bigrams Bigrams.cpp)

target_link_libraries(Bigrams 
    GraphanLib
    TrigramLib
)
