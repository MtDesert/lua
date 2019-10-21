cmake_minimum_required(VERSION 2.8)
project(lua)
include(../CompileScripts/CMakeLists.txt)
#处理报错情况
if(${TARGET_SYSTEM_NAME} STREQUAL Android)
	add_definitions(-Wno-deprecated)
endif()
#编译源代码
aux_source_directory(src SRC_LIST)
add_library(${PROJECT_NAME} SHARED ${SRC_LIST})