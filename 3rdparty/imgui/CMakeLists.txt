# Note: we are not including files under backend/ here: those are #included in project main source files
file(GLOB IMGUI_HEDAER ${CMAKE_CURRENT_LIST_DIR}/*.h)
file(GLOB IMGUI_SOURCE ${CMAKE_CURRENT_LIST_DIR}/*.cpp)
add_library(imgui
	${IMGUI_HEDAER}
	${IMGUI_SOURCE}
)
target_include_directories(imgui PUBLIC ${CMAKE_CURRENT_LIST_DIR})
