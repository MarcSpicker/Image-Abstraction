cmake_minimum_required(VERSION 3.10)

SET(project_name "synth")
project (${project_name})

SET(SOURCES 
    tree_of_shapes.c
)

include_directories(
    $<TARGET_PROPERTY:mw3,INTERFACE_INCLUDE_DIRECTORIES>
    $<TARGET_PROPERTY:flst,INTERFACE_INCLUDE_DIRECTORIES>
)

add_library(${project_name} OBJECT ${SOURCES})

target_include_directories(${project_name}
    PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}
)
