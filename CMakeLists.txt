cmake_minimum_required(VERSION 3.20)

project(opencv)

set(CMAKE_CXX_STANDARD 17)

add_library(${PROJECT_NAME} INTERFACE IMPORTED GLOBAL)

target_include_directories(
  ${PROJECT_NAME}
  INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}/include/opencv4
  INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}/include/opencv4/opencv2)
file(GLOB_RECURSE SO_FILES "lib/*.so")
target_link_libraries(${PROJECT_NAME} INTERFACE ${SO_FILES})
