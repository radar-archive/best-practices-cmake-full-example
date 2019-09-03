# Copyright 2019 RADAR, Inc. - All Rights Reserved
# Proprietary and confidential

cmake_minimum_required(VERSION 3.7)

set(ROOT $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../../..>)

add_library(libll
  ${ROOT}/src/ll/ll.hpp
  ${ROOT}/src/ll/ll.cpp
  )

target_include_directories(libll PUBLIC ${ROOT}/src)
