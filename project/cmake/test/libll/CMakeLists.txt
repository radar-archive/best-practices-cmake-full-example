# Copyright 2019 RADAR, Inc. - All Rights Reserved
# Proprietary and confidential

cmake_minimum_required(VERSION 3.8)

enable_testing()

set(ROOT $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../../../..>)

macro(local_run TESTNAME)
  add_test(NAME ${TESTNAME} COMMAND ${TESTNAME} WORKING_DIRECTORY ${ROOT})

  add_executable(${TESTNAME} ${ARGN})

  target_link_libraries(${TESTNAME} PUBLIC libll)

  target_link_libraries(${TESTNAME} PUBLIC Boost::boost)
endmacro()

local_run(test_ll ${ROOT}/test/ll/test_ll.cpp)

find_package(Boost REQUIRED)
