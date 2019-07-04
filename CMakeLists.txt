cmake_minimum_required(VERSION 3.10)

project(Image-Abstraction)

set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_CXX_STANDARD 11)

set(PROJECT_DIR ${PROJECT_SOURCE_DIR})

# add headers to project
set(HEADERS
    ${PROJECT_DIR}/AbstractionProcess.h
    ${PROJECT_DIR}/ImageLabel.h
    ${PROJECT_DIR}/ImageViewer.h
    ${PROJECT_DIR}/ImageWidget.h
    ${PROJECT_DIR}/OptionWidget.h
    ${PROJECT_DIR}/Segmentation.h
    ${PROJECT_DIR}/TreeOfShapes.h
)

# add sources to project
set(SOURCES
    ${PROJECT_DIR}/main.cpp
    ${PROJECT_DIR}/AbstractionProcess.cpp
    ${PROJECT_DIR}/ImageLabel.cpp
    ${PROJECT_DIR}/ImageViewer.cpp
    ${PROJECT_DIR}/ImageWidget.cpp
    ${PROJECT_DIR}/OptionWidget.cpp
    ${PROJECT_DIR}/Segmentation.cpp
    ${PROJECT_DIR}/TreeOfShapes.cpp
)

# Qt5
find_package(Qt5 5.10 COMPONENTS Widgets REQUIRED)

# mw3
add_subdirectory(src/mw3)
# flst
add_subdirectory(src/flst)
# iio
add_subdirectory(src/iio)
# kdtree
add_subdirectory(src/kdtree)
# segment
add_subdirectory(src/segment)
# synth
add_subdirectory(src/synth)

include_directories(
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${Qt5Widgets_INCLUDE_DIRS}
)

add_executable(${PROJECT_NAME}
    ${HEADERS}
    ${SOURCES}
)

target_link_libraries(${PROJECT_NAME} 
    mw3
    flst
    IIOLIB
    kdtree
    segment
    synth
    Qt5::Widgets
)
