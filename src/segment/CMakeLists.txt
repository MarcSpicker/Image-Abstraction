cmake_minimum_required(VERSION 3.10)

SET(project_name "segment")
project (${project_name})

SET(SOURCES 
    disjoint-set.cpp
)

add_library(${project_name} OBJECT ${SOURCES})

target_include_directories(${project_name}
    PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}
)
