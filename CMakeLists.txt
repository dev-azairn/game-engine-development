cmake_minimum_required(VERSION 3.15)

project(Engine)

find_package(OpenGL REQUIRED)


add_subdirectory("glfw")

add_executable(Engine index.cpp)

target_link_libraries(Engine glfw)
