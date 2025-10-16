cmake_minimum_required(VERSION 3.16)

project(Engine)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)

find_package(OpenGL REQUIRED)
find_package(Vulkan REQUIRED)
find_package(glm REQUIRED)

add_subdirectory(glad)
add_subdirectory(glfw)
add_subdirectory(glm)

add_custom_target(copy_assets
    COMMAND ${CMAKE_COMMAND} -E copy_directory ${CMAKE_CURRENT_LIST_DIR}/shaders
    ${CMAKE_CURRENT_BINARY_DIR}/shaders
)

add_executable(Engine main.cpp)

target_link_libraries(Engine PRIVATE glfw)
target_link_libraries(Engine PRIVATE GLAD)
target_link_libraries(Engine PRIVATE Vulkan::Vulkan)
target_link_libraries(Engine PRIVATE glm::glm)
add_dependencies(Engine copy_assets)


