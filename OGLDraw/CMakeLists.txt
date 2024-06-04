
set(APP OGLDraw)

file(GLOB SOURCES "${CMAKE_CURRENT_SOURCE_DIR}/*.cpp" 
	              "${CMAKE_CURRENT_SOURCE_DIR}/*.h" )
				  
source_group("sources" FILES ${SOURCES})

add_executable(${APP} ${SOURCES})

target_link_libraries(${APP} Qt5::Core Qt5::Gui Qt5::Widgets)
target_link_libraries(${APP} opengl32)

