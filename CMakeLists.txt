cmake_minimum_required(VERSION 3.16)

project(Engine)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)

add_subdirectory(lib)

file(GLOB_RECURSE SOURCES src/*.cpp)
add_executable(Engine ${SOURCES})

target_link_libraries(Engine PRIVATE Lib)


