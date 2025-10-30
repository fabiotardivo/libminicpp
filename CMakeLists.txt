cmake_minimum_required(VERSION 3.28)
project(libminicpp CXX)

# C++
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Sources
set(LIBMINICPP_SRC
    acstr.cpp
    bitset.cpp
    constraint.cpp
    domain.cpp
    domain.cpp
    fail.cpp
    intvar.cpp
    lex.cpp
    mallocWatch.cpp
    matching.cpp
    regular.cpp
    RuntimeMonitor.cpp
    search.cpp
    solver.cpp
    store.cpp
    table.cpp
    trailable.cpp
    trail.cpp
)

# Library
add_library(libminicpp ${LIBMINICPP_SRC})
set_target_properties(libminicpp PROPERTIES PREFIX "")
target_include_directories(libminicpp PUBLIC ${PROJECT_SOURCE_DIR})

# Demo
if(PROJECT_IS_TOP_LEVEL)
    add_executable(minicpp-nqueens Demo.cpp)
    target_link_libraries(minicpp-nqueens PRIVATE libminicpp)
endif()