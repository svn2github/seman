project(MAPost)

list (APPEND LIB_DEPENDS 
    MAPostLib
    GerPostMorph
)

CompileIDL(${PROJECT_NAME})

add_library(${PROJECT_NAME} SHARED
MAPost.cpp
MAPost.def
MAPost.rc
MAPostCOM.cpp
StdAfx.cpp
)


target_link_libraries(${PROJECT_NAME}
    ${LIB_DEPENDS}
)

CopyAndRegsvr(${PROJECT_NAME})
