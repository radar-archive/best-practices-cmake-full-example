cmake_minimum_required(VERSION 3.7)

add_executable(example ../../../src/example/example.cpp)

target_link_libraries(example PRIVATE libll libtl)
