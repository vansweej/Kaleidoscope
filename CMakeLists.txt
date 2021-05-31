cmake_minimum_required(VERSION 3.19)

set(CMAKE_CXX_STANDARD 20)

project(Kaleidoscope)

find_package(LLVM REQUIRED CONFIG)

include_directories( ${LLVM_INCLUDE_DIRS} )
add_definitions( ${LLVM_DEFINITIONS} )

add_executable(Kaleidoscope main.cpp)

llvm_map_components_to_libnames(llvm_libs support core irreader)

target_link_libraries(Kaleidoscope ${llvm_libs})
