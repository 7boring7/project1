cmake_minimum_required(VERSION 3.10)
project(project1) 

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

add_compile_options(-pthread)

include_directories(${CMAKE_SOURCE_DIR}/include)
link_directories(${CMAKE_SOURCE_DIR}/lib)

file(GLOB CPP_SOURCES "src/*.cpp")
file(GLOB_RECURSE REMOVE_CMAKE "cmake-build-debug/*")
list(REMOVE_ITEM ${CPP_SOURCES} ${REMOVE_CMAKE})
add_executable(${PROJECT_NAME}  ${CPP_SOURCES})