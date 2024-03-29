# MIT License

# Copyright (c) 2018 Libavius

# Permission is hereby granted, free of charge, to any person obtaining a copy
# of this software and associated documentation files (the "Software"), to deal
# in the Software without restriction, including without limitation the rights
# to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
# copies of the Software, and to permit persons to whom the Software is
# furnished to do so, subject to the following conditions:

# The above copyright notice and this permission notice shall be included in all
# copies or substantial portions of the Software.

# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
# AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
# OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
# SOFTWARE.

cmake_minimum_required(VERSION 3.5)

### options
option(WARNINGS "ON - display compiler warnings, OFF - do not display compiler warnings" ON)
option(OPENMP "ON - enables adding of OpenMP targets, OFF - disables adding of OpenMP targets" OFF)
option(PFUNIT "ON - using pFUnit for unit tests, OFF - skip building unit tests" OFF)

# defines project name and used language
project(FortranTemplate Fortran)

# sets compiler flags
include(cmake/utils/setFlags.cmake)

# sets path for executables
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_CURRENT_BINARY_DIR}/bin)

# adds custom cmake functions
include(cmake/utils/fortranFunctions.cmake)

# adding pFUnit support
include(cmake/utils/pFUnit.cmake)

# adds subdirectories
# add_subdirectory(utils)
add_subdirectory(src)

