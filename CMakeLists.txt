cmake_minimum_required(VERSION 3.13)
project(ImGuiDemoProject LANGUAGES C CXX)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(OpenGL REQUIRED)
add_subdirectory(3rdparty/glfw)
add_subdirectory(3rdparty/glad)
add_subdirectory(3rdparty/imgui)

add_executable(${PROJECT_NAME}
    # add_executable requires at least one source file
    source/main.cpp
)
add_subdirectory(source)

target_include_directories(${PROJECT_NAME} PRIVATE sources/)
target_link_libraries(${PROJECT_NAME}
PRIVATE
    OpenGL::GL
    glfw
    glad
    imgui
)
