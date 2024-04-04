cmake_minimum_required(VERSION 3.12)

project(Analysis-1 NONE)
include(UseLATEX)

add_custom_target(
    writegitid ALL
    COMMAND ${CMAKE_CURRENT_SOURCE_DIR}/write-gitid.sh
    WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}
)

set(IMAGE_DIRS
    img
    # Add subdirectories here
    # img/logic
    # img/rca
)

add_latex_document(
    Analysis-1.tex
    FORCE_PDF
    IMAGE_DIRS ${IMAGE_DIRS}
    DEPENDS writegitid
)

add_latex_document(
    Analysis_1_ma.tex
    FORCE_PDF
    IMAGE_DIRS ${IMAGE_DIRS}
    DEPENDS writegitid
)
