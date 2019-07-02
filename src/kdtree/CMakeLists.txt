cmake_minimum_required(VERSION 3.10)

SET(project_name "kdtree")
project (${project_name})

SET(SOURCES 
    ann/src/ANN.cpp
    ann/src/bd_fix_rad_search.cpp
    ann/src/bd_pr_search.cpp
    ann/src/bd_search.cpp
    ann/src/bd_tree.cpp
    ann/src/brute.cpp
    ann/src/kd_dump.cpp
    ann/src/kd_fix_rad_search.cpp
    ann/src/kd_pr_search.cpp
    ann/src/kd_search.cpp
    ann/src/kd_split.cpp
    ann/src/kd_tree.cpp
    ann/src/kd_util.cpp
    ann/src/perf.cpp
)

add_library(${project_name} OBJECT ${SOURCES})

target_include_directories(${project_name}
    PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}
        ${CMAKE_CURRENT_SOURCE_DIR}/src
        ${CMAKE_CURRENT_SOURCE_DIR}/ann/include
)
