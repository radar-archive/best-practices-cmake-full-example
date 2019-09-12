.. Copyright 2019 RADAR, Inc. - All Rights Reserved
.. Proprietary and confidential

CMake Full Example
==================

.. contents::

There is a larger example with several libraries, executables, and
unit tests defined. The structure is laid out as in the Boost.Build
example to help live next to them, have commonality.

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

.. code::

   mkdir -p build
   cd build
   cmake ..
   cd ..
   cmake --build build
   cmake --build build --target test
