cmake_minimum_required(VERSION 2.8)

project("qu3e")

set(qu3e_version 1.1)

option(qu3e_build_shared "Build qu3e shared libraries" OFF)
option(qu3e_build_static "Build qu3e static libraries" ON)
option(qu3e_build_demo "Build qu3e demo" ON)

add_subdirectory(src)

if(qu3e_build_demo)
	find_package(OpenGL REQUIRED)
	add_subdirectory(freeglut)
	add_subdirectory(demo)
	add_subdirectory(imgui)
endif()
