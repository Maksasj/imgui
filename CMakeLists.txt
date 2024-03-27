cmake_minimum_required(VERSION 3.21)
project(imgui)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_BUILD_TYPE release)

# imgui headers require glfw headers
include_directories("../glfw/include")

include_directories("./")
include_directories("./backends")

file(GLOB SRC_FILES
    "*.cpp"
    "backends/imgui_impl_glfw.cpp"
    "backends/imgui_impl_opengl3.cpp"
)

add_library(imgui STATIC ${SRC_FILES})