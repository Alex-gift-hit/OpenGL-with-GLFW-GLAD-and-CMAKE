cmake_minimum_required(VERSION 3.14)
project(my_app)

find_package(OpenGL REQUIRED)

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)

add_subdirectory(3rdparty/glfw-3.3.8)
add_subdirectory(3rdparty/glad)

add_executable(my_app main.cpp)

target_link_libraries(my_app glad)
target_link_libraries(my_app OpenGL::GL)
target_link_libraries(my_app glfw)
