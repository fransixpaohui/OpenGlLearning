CMAKE_MINIMUM_REQUIRED(VERSION 3.0)
PROJECT(DeepTest)

set(OPENGL_PATH "D:/Tools/OpenGL")
set(GLAD_C_PATH "D:/Tools/glad/src")
set(ASSIMP_PATH "D:/Tools/assimp/assimp-5.4.2")

#头文件包含目录
include_directories(${OPENGL_PATH}/includes)
include_directories(${ASSIMP_PATH}/include)
include_directories(${ASSIMP_PATH}/build/include)

#引入库 glfw3.lib
FIND_LIBRARY(GLFW_LIB glfw3 ${OPENGL_PATH}/lib)
link_libraries(${GLFW_LIB})

find_library(ASSIMP_LIB assimp-vc143-mt ${ASSIMP_PATH}/build/lib/Release)
link_libraries(${ASSIMP_LIB})

add_executable(
	DeepTest
	src/DeepTest.cpp
	${GLAD_C_PATH}/glad.c
	"src/shader.h"
	"src/stb_image.h"
	"src/camera.h"
	"src/mesh.h"
	"src/model.h"
 )