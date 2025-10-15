cmake_minimum_required(VERSION 3.16)

project(Engine)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)
find_package(OpenGL REQUIRED)
find_package (Vulkan REQUIRED)


add_subdirectory(glad)
add_subdirectory("glfw")

add_executable(Engine index.cpp)

target_link_libraries(Engine PRIVATE glfw)
target_link_libraries(Engine PRIVATE GLAD)
target_link_libraries(Engine PRIVATE Vulkan::Vulkan)
target_link_libraries(Engine PRIVATE Vulkan::Headers)
# set up Vulkan C++ module


