cmake_minimum_required(VERSION 3.3...4.0)
project(LearnOpenGL)

set(CMAKE_CXX_STANDARD 20)

#Find glfw3 and OpenGL
find_package(glfw3 CONFIG REQUIRED)
find_package(OpenGL REQUIRED)

#add all resources/shaders
file(COPY ${CMAKE_CURRENT_SOURCE_DIR}/resources DESTINATION ${CMAKE_CURRENT_BINARY_DIR})

include_directories(include)

add_executable(1.7.textures src/1.7.textures.cpp src/Shader.cpp src/glad.c)
add_executable(1.8.transformations src/1.8.transformations.cpp src/Shader.cpp src/glad.c)
add_executable(1.9.coordinatesystems src/1.9.coordinatesystems.cpp src/Shader.cpp src/glad.c)

target_link_libraries(1.7.textures PUBLIC glfw OpenGL::GL)
target_link_libraries(1.8.transformations PUBLIC glfw OpenGL::GL)
target_link_libraries(1.9.coordinatesystems PUBLIC glfw OpenGL::GL)

