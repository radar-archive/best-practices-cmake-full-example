CMake Full Example
==================

.. contents::

This is an example CMake build system that attempts to illustrate the
approach described in the guidelines below.  The CMake build requires
CMake 3.7 or later.

This project contains a C++ main program, a C++ library and tests, and
a C++ template library and tests.

To build and run the tests for the example, run the following commands
from the root directory.

.. code::

   cd example
   mkdir -p build
   cd build
   cmake -G Xcode ..
   cd ..
   cmake --build build
