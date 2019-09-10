CMake Full Example
==================

.. contents::

This is an example CMake build system that attempts to illustrate the
approach described in the guidelines below.  The CMake build requires
CMake 3.7 or later.

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
