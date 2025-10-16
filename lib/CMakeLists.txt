find_package(OpenGL REQUIRED)
find_package(Vulkan REQUIRED)

add_subdirectory(glad)
add_subdirectory(glfw)

add_library(Lib INTERFACE)

target_link_libraries(Lib INTERFACE glfw)
target_link_libraries(Lib INTERFACE GLAD)
target_link_libraries(Lib INTERFACE Vulkan::Vulkan)
