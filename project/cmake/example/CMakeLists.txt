# Copyright 2019 RADAR, Inc. - All Rights Reserved
# Proprietary and confidential

cmake_minimum_required(VERSION 3.8)

add_executable(example ../../../src/example/example.cpp)

target_link_libraries(example PRIVATE libll)
target_link_libraries(example PRIVATE libtl)

target_compile_features(example PRIVATE cxx_std_14)
set_target_properties(example PROPERTIES CXX_EXTENSIONS OFF)
