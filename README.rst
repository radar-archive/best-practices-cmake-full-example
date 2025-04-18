.. Copyright 2019 RADAR, Inc. - All Rights Reserved
.. Proprietary and confidential

CMake Full Example
==================

.. contents::

This example contains a larger example with several libraries,
executables, and unit tests defined. The structure is laid out as in
the Boost.Build examples to help live next to them, have commonality.

The full example requires Boost.Test from the Boost C++ Libraries is
installed on the system.

.. code::

   ./.gitignore
   ./CMakeLists.txt
   ./Jamroot
   ./project/bb
   ./project/cmake/p0/CMakeLists.txt
   ./project/cmake/p1/CMakeLists.txt
   ./project/cmake/libl0/CMakeLists.txt
   ./project/cmake/libl1/CMakeLists.txt
   ./project/cmake/test/libl0/CMakeLists.txt
   ./project/cmake/test/libl1/CMakeLists.txt
   ./src/libl0/*.?pp
   ./src/libl1/*.?pp
   ./test/libl0/*.?pp
   ./test/libl1/*.?pp

To build and run the tests for the example, run the following commands
from the root directory.

.. code:: sh

   mkdir -p build && cd build && cmake -DCMAKE_INSTALL_PREFIX=/tmp/cmake-best-practices .. && cd ..
   cmake --build build
   cmake --build build --target test
   cmake --build build --target install
