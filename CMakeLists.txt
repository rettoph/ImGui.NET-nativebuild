cmake_minimum_required(VERSION 3.1)

project(cimgui)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

#general settings
file(GLOB IMGUI_SOURCES
    cimgui/imgui/imgui.cpp
    cimgui/imgui/imgui_draw.cpp
    cimgui/imgui/imgui_demo.cpp
    cimgui/imgui/imgui_widgets.cpp
	cimgui/imgui/imgui_tables.cpp
)

add_library(cimgui SHARED 
    cimgui/cimgui.cpp
    ${IMGUI_SOURCES}
)

target_compile_definitions(cimgui PUBLIC IMGUI_DISABLE_OBSOLETE_FUNCTIONS=1)

set_target_properties(cimgui PROPERTIES PREFIX "")


add_library(cimplot SHARED
    ${IMGUI_SOURCES}
    cimplot/cimplot.cpp
    cimplot/implot/implot.cpp
    cimplot/implot/implot_demo.cpp
    cimplot/implot/implot_items.cpp)

target_compile_definitions(cimplot PUBLIC IMGUI_DISABLE_OBSOLETE_FUNCTIONS=1)

target_include_directories(cimplot PUBLIC cimgui)
target_include_directories(cimplot PUBLIC cimgui/imgui)

set_target_properties(cimplot PROPERTIES PREFIX "")