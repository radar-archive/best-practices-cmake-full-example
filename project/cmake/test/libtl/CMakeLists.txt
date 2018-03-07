cmake_minimum_required(VERSION 3.7)

enable_testing()

set(ROOT $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../../../..>)

macro(local_run TESTNAME)
  add_executable(${TESTNAME} ${ARGN})

  add_test(NAME run_${TESTNAME} COMMAND ${TESTNAME} WORKING_DIRECTORY ${ROOT})

  target_link_libraries(${TESTNAME} PUBLIC libtl)
endmacro()

local_run(test_tl ${ROOT}/test/tl/test_tl.cpp)
