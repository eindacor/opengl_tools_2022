cmake_minimum_required(VERSION 3.23)
project(opengl_tools)

set(CMAKE_CXX_STANDARD 14)

add_compile_definitions(GLEW_STATIC)

# set root dir for precompiled glew/glfw (32 bit) binaries
set(GLEW_GLFW_PATH C:/dev)

include_directories(${GLEW_GLFW_PATH}/glfw-3.3.8.bin.WIN32/include)
link_directories(${GLEW_GLFW_PATH}/glfw-3.3.8.bin.WIN32/lib-mingw)

include_directories(${GLEW_GLFW_PATH}/glew-2.2.0/include)
link_directories(${GLEW_GLFW_PATH}/glew-2.2.0/lib/Release/Win32)

include_directories(${GLEW_GLFW_PATH}/glm/glm)

add_library(opengl_tools STATIC obj_parser.cpp ogl_tools.cpp ogl_tools.h)

target_link_libraries(opengl_tools glew32s glfw3 glu32 opengl32)
