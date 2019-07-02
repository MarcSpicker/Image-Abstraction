cmake_minimum_required(VERSION 3.10)

SET(project_name "mw3")
project (${project_name})

SET(SOURCES 
    ccimage.c
    ccmovie.c
    cfimage.c
    cimage.c
    error.c
    fderiv.c
    fimage.c
    fsepconvol.c
    fsignal.c
    libmw.c
    list.c
    ll_boundaries2.c
    modes_circ.c
    sconst.c
    sgauss.c
    shape.c
)

add_library(${project_name} OBJECT ${SOURCES})

target_include_directories(${project_name}
    PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}
)
