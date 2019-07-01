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

# flst
file(GLOB flst_HEADERS "src/flst/*.h")
file(GLOB flst_SOURCES "src/flst/*.c")

# iio
file(GLOB iio_HEADERS "src/iio/*.h")

# kdtree
file(GLOB kdtree_HEADERS "src/kdtree/*.h")
file(GLOB kdtree_ann_HEADERS "src/kdtree/ann/include/ANN/*.h")
file(GLOB kdtree_ann_SOURCE "src/kdtree/ann/src/*.cpp")

# mw3
file(GLOB mw3_HEADERS "src/mw3/*.h")
file(GLOB mw3_SOURCES "src/mw3/*.c")

# segment
file(GLOB segment_HEADERS "src/segment/*.h")
file(GLOB segment_SOURCES "src/segment/*.cpp")

# synth
file(GLOB synth_HEADERS "src/synth/*.h")
file(GLOB synth_SOURCES "src/synth/*.c")

include_directories(
        ${CMAKE_CURRENT_SOURCE_DIR}
        ${CMAKE_CURRENT_SOURCE_DIR}/src/flst
        ${CMAKE_CURRENT_SOURCE_DIR}/src/mw3
        ${CMAKE_CURRENT_SOURCE_DIR}/src/segment
        ${CMAKE_CURRENT_SOURCE_DIR}/src/synth
        ${CMAKE_CURRENT_SOURCE_DIR}/src/kdtree
        ${CMAKE_CURRENT_SOURCE_DIR}/src/kdtree/ann/include
)

find_package(Qt5 5.10 COMPONENTS Widgets REQUIRED)

add_executable(
        ${PROJECT_NAME}
        ${HEADERS}
        ${SOURCES}
        ${flst_HEADERS}
        ${flst_SOURCES}
        ${iio_HEADERS}
        ${kdtree_HEADERS}
        ${kdtree_ann_HEADERS}
        ${kdtree_ann_SOURCE}
        ${mw3_HEADERS}
        ${mw3_SOURCES}
        ${segment_HEADERS}
        ${segment_SOURCES}
        ${synth_HEADERS}
        ${synth_SOURCES}
)

target_link_libraries(${PROJECT_NAME} 
        Qt5::Widgets
)
