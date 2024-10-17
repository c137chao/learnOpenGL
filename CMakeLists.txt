cmake_minimum_required(VERSION 3.24)
project(learnOpengl)
project(helloWindow)

set(CMAKE_CXX_STANDARD 17)

set(SRC_DIR ${PROJECT_SOURCE_DIR}/src)
set(HED_DIR ${PROJECT_SOURCE_DIR}/include)

set(SOURCES ${SRC_DIR}/glad.c ${SRC_DIR}/helloWindow.cpp)

include_directories(${HED_DIR}/ ${HED_DIR})

find_package(glfw3 REQUIRED)
find_package(OpenGL REQUIRED)

add_executable(helloWindow ${SOURCES})

target_include_directories(helloWindow PUBLIC ${OPENGL_INCLUDE_DIR})

target_link_libraries(helloWindow "-framework Cocoa")
target_link_libraries(helloWindow "-framework IOKit")
target_link_libraries(helloWindow "-framework OpenGL")

target_link_libraries(helloWindow glfw ${OPENGL_gl_LIBRARY})