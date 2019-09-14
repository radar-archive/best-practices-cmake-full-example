# Copyright 2019 RADAR, Inc. - All Rights Reserved
# Proprietary and confidential

cmake_minimum_required(VERSION 3.8)

project(full-example)

enable_testing()

add_subdirectory(project/cmake/example)

add_subdirectory(project/cmake/libll)
add_subdirectory(project/cmake/test/libll)

add_subdirectory(project/cmake/libtl)
add_subdirectory(project/cmake/test/libtl)
