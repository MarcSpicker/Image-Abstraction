cmake_minimum_required(VERSION 3.10)

SET(project_name "flst")
project (${project_name})

SET(SOURCES 
    flstb_boundary.c
    flstb_dual.c
    flstb_dualchain.c
    flst_bilinear.c
    flst_boundary.c
    flstb_quantize.c
    flst.c
    flst_pixels.c
    flst_reconstruct.c
    fsaddles.c
)

include_directories($<TARGET_PROPERTY:mw3,INTERFACE_INCLUDE_DIRECTORIES>)

add_library(${project_name} OBJECT ${SOURCES})

target_include_directories(${project_name}
    PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}
)
