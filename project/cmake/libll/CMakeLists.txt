# Copyright 2019 RADAR, Inc. - All Rights Reserved
# Proprietary and confidential

cmake_minimum_required(VERSION 3.8)

set(ROOT $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../../..>)

add_library(libll
  ${ROOT}/src/ll/ll.cpp
  ${ROOT}/src/ll/ll.hpp)

set_target_properties(libll PROPERTIES PUBLIC_HEADER
  ${ROOT}/src/ll/ll.hpp)

target_include_directories(libll PUBLIC
  $<BUILD_INTERFACE:${ROOT}/src>
  $<INSTALL_INTERFACE:include>)

target_compile_features(libll PRIVATE cxx_std_14)
set_target_properties(libll PROPERTIES CXX_EXTENSIONS OFF)

install(TARGETS libll
  EXPORT libll
  LIBRARY DESTINATION lib
  ARCHIVE DESTINATION lib
  RUNTIME DESTINATION bin
  PUBLIC_HEADER DESTINATION include/ll)

install(EXPORT libll
  NAMESPACE full-example::
  DESTINATION lib/cmake/full-example
  FILE libllConfig.cmake)
