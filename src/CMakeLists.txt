cmake_minimum_required(VERSION 3.16)
project(CppWeb VERSION 0.0.1)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(Threads REQUIRED)

include_directories(include)

file(GLOB_RECURSE SOURCES "src/*.cpp")
add_library(cppweb ${SOURCES})

target_link_libraries(cppweb Threads::Threads)

add_executable(basic_api examples/basic_api/main.cpp)
target_link_libraries(basic_api cppweb)