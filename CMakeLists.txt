cmake_minimum_required(VERSION 3.24)

set(CMAKE_TOOLCHAIN_FILE ${CMAKE_SOURCE_DIR}/project/ARMCC.cmake)
include(${CMAKE_SOURCE_DIR}/project/Global.cmake)
set_toolchain()

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

project(nw C CXX)

__compiler_armcc(C)
__compiler_armcc(CXX)

file(GLOB_RECURSE SOURCES */src/*.c */src/*.cpp)

add_library(nw ${SOURCES})

target_include_directories(nw PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/anim/include)
target_include_directories(nw PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/font/include)
target_include_directories(nw PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/gfx/include)
target_include_directories(nw PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/lyt/include)
target_include_directories(nw PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/snd/include)
target_include_directories(nw PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/ut/include)
