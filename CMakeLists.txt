cmake_minimum_required(VERSION 2.8.9)
project(gldeps)

add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/glfw)
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/gl3w)

set(GLDEPS_INCLUDE_DIRS
  ${CMAKE_CURRENT_SOURCE_DIR}/glfw/include
  ${CMAKE_CURRENT_SOURCE_DIR}/gl3w/include
  ${CMAKE_CURRENT_SOURCE_DIR}/glm
  CACHE STRING "Include directories of gldeps")

set(GLDEPS_LIBRARIES
  glfw ${GLFW_LIBRARIES}
  gl3w
  CACHE STRING "Dependencies of gldeps")
