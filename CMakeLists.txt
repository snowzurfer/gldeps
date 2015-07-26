cmake_minimum_required(VERSION 2.8.9)
project(gldeps)

add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/glfw)
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/gl3w)
add_library(imgui STATIC
  ${CMAKE_CURRENT_SOURCE_DIR}/imgui/imgui.h
  ${CMAKE_CURRENT_SOURCE_DIR}/imgui/imconfig.h
  ${CMAKE_CURRENT_SOURCE_DIR}/imgui/imgui.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/imgui/stb_rect_pack.h
  ${CMAKE_CURRENT_SOURCE_DIR}/imgui/stb_textedit.h
  ${CMAKE_CURRENT_SOURCE_DIR}/imgui/stb_truetype.h)

set(GLDEPS_INCLUDE_DIRS
  ${CMAKE_CURRENT_SOURCE_DIR}/glfw/include
  ${CMAKE_CURRENT_SOURCE_DIR}/gl3w/include
  ${CMAKE_CURRENT_SOURCE_DIR}/glm
  ${CMAKE_CURRENT_SOURCE_DIR}/imgui
  CACHE STRING "Include directories of gldeps")

set(GLDEPS_LIBRARIES
  glfw ${GLFW_LIBRARIES}
  gl3w
  imgui
  CACHE STRING "Dependencies of gldeps")
