cmake_minimum_required(VERSION 3.0.0)
project(3D_ENGINE VERSION 0.1.0 LANGUAGES C CXX)

include(CTest)
enable_testing()

find_package(OpenGL REQUIRED)
find_package(glfw3 3.3 REQUIRED)

add_library(GLAD "include/glad/glad.c")

add_executable(3D_ENGINE main.cpp)

set(LIBS glfw ${GLFW3_LIBRARY} ${OPENGL_LIBRARY} GLAD)

target_link_libraries(${PROJECT_NAME} ${LIBS})

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
