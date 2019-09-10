# Copyright 2019 RADAR, Inc. - All Rights Reserved
# Proprietary and confidential

cmake_minimum_required(VERSION 3.8)

enable_testing()

set(ROOT $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../../../..>)

macro(local_run TESTNAME)
  add_executable(${TESTNAME} ${ARGN})

  add_test(NAME run_${TESTNAME} COMMAND ${TESTNAME} WORKING_DIRECTORY ${ROOT})

  target_link_libraries(${TESTNAME} PUBLIC libtl)

  target_link_libraries(${TESTNAME} PUBLIC Boost::boost)
endmacro()

local_run(test_tl ${ROOT}/test/tl/test_tl.cpp)

find_package(Boost)
