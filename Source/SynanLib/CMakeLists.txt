cmake_minimum_required(VERSION 3.5)

project(SynanLib)

add_library(SynanLib
SentencesCollection.cpp
SyntaxHolder.cpp
)

target_link_libraries(SynanLib
    LemmatizerLib
    GerPostMorph
    MAPostLib
    SimpleGrammarLib
    SynCommonLib
    RusSynanLib
    GerSynanLib
    EngSynanLib
)

if (BUILD_DICTS)
    add_dependencies(SynanLib Ross)
endif()
