cmake_minimum_required(VERSION 3.15.0)

project(OpenGL)
SET(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_HOME_DIRECTORY}/Binary CACHE PATH "Directory for bin" )

set(CMAKE_CXX_STANDARD 17)

if ( NOT CMAKE_BUILD_TYPE )
	set ( CMAKE_BUILD_TYPE "Debug" CACHE STRING "Set build type" FORCE )
	set_property ( CACHE CMAKE_BUILD_TYPE PROPERTY STRINGS Release Debug RelWithDebInfo )
endif ( )

if(MSVC)
	add_compile_options("/MP")	
endif()

if(UNIX)
    find_package(Qt5 COMPONENTS Widgets X11Extras REQUIRED)
else()
    find_package(Qt5 COMPONENTS Widgets REQUIRED)
endif()

add_subdirectory(OGLDraw)
add_subdirectory(OGLPyramid)
add_subdirectory(OGLQuad)
