cmake_minimum_required(VERSION 3.7)

set(ROOT $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../../..>)

add_library(libtl INTERFACE)

target_sources(libtl INTERFACE
  ${ROOT}/src/tl/tl.hpp
  )

target_include_directories(libtl INTERFACE ${ROOT}/src)
