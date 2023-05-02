cmake_minimum_required(VERSION 3.1)

project(cimgui)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)


add_library(cimgui SHARED 
    cimgui/cimgui.cpp
    cimgui/cimgui_impl.cpp
    cimgui/imgui/imgui.cpp
    cimgui/imgui/imgui_draw.cpp
    cimgui/imgui/imgui_demo.cpp
    cimgui/imgui/imgui_widgets.cpp
	cimgui/imgui/imgui_tables.cpp
    cimgui/imgui/backends/imgui_impl_win32.cpp
    cimgui/imgui/backends/imgui_impl_dx11.cpp)

target_compile_definitions(cimgui PUBLIC IMGUI_DISABLE_OBSOLETE_FUNCTIONS=1)
target_compile_definitions(cimgui PUBLIC CIMGUI_USE_WIN32=1)
target_compile_definitions(cimgui PUBLIC CIMGUI_USE_DX11=1)
target_include_directories(cimgui PUBLIC cimgui/imgui)
set_target_properties(cimgui PROPERTIES PREFIX "")


add_library(cimplot SHARED
    cimgui/imgui/imgui.cpp
    cimgui/imgui/imgui_draw.cpp
    cimgui/imgui/imgui_demo.cpp
    cimgui/imgui/imgui_widgets.cpp
	cimgui/imgui/imgui_tables.cpp
    cimplot/cimplot.cpp
    cimplot/implot/implot.cpp
    cimplot/implot/implot_demo.cpp
    cimplot/implot/implot_items.cpp)

target_include_directories(cimplot PUBLIC cimgui/imgui)
set_target_properties(cimplot PROPERTIES PREFIX "")


add_library(cimguizmo SHARED
    cimgui/imgui/imgui.cpp
    cimgui/imgui/imgui_draw.cpp
    cimgui/imgui/imgui_demo.cpp
    cimgui/imgui/imgui_widgets.cpp
	cimgui/imgui/imgui_tables.cpp
    cimguizmo/cimguizmo.cpp
    cimguizmo/ImGuizmo/ImGuizmo.cpp)

target_include_directories(cimguizmo PUBLIC cimgui/imgui)
set_target_properties(cimguizmo PROPERTIES PREFIX "")