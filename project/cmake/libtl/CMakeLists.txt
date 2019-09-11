# Copyright 2019 RADAR, Inc. - All Rights Reserved
# Proprietary and confidential

cmake_minimum_required(VERSION 3.8)

set(ROOT $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../../..>)

add_library(libtl INTERFACE)

target_sources(libtl INTERFACE ${ROOT}/src/tl/tl.hpp)

target_include_directories(libtl INTERFACE
  $<BUILD_INTERFACE:${ROOT}/src>
  $<INSTALL_INTERFACE:include>)

install(TARGETS libtl
  EXPORT libtl)

install(FILES ${ROOT}/src/tl/tl.hpp
  DESTINATION include/tl)

install(EXPORT libtl
  NAMESPACE example_
  DESTINATION lib/cmake/example)
