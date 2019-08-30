---
title: CMake
description: CMake
published: true
date: 2019-08-30T09:47:15.602Z
tags: 
---

# CMake

CMake is an extensible, open-source system that manages the build process in an operating system and in a compiler-independent manner

Simple configuration files placed in each source directory (called CMakeLists.txt files) are used to generate standard build files (e.g., makefiles on Unix and projects/workspaces in Windows MSVC) which are used in the usual way.

CMake can generate a native build environment that will compile source code, create libraries, generate wrappers and build executables in arbitrary combinations. CMake supports in-place and out-of-place builds, and can therefore support multiple builds from a single source tree.

CMake also supports static and dynamic library builds. Another nice feature of CMake is that it generates a cache file that is designed to be used with a graphical editor. For example, when CMake runs, it locates include files, libraries, and executables, and may encounter optional build directives. This information is gathered into the cache, which may be changed by the user prior to the generation of the native build files.

# Installation in REDHAT
yum install cmake

For the below simple test.cpp:
`// test.cpp

#include <iostream>

using namespace std;

int main(void) {

     cout << "Hello World" << endl;

     return(0);

}
`
  We would need to create CMakeLists.txt 
  # Specify the minimum version for CMake

cmake_minimum_required(VERSION 2.8)

# Project's name

project(hello)
# Set the output folder where your program will be created
set(CMAKE_BINARY_DIR ${CMAKE_SOURCE_DIR}/bin)
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR})
set(LIBRARY_OUTPUT_PATH ${CMAKE_BINARY_DIR})

# The following folder will be included
include_directories("${PROJECT_SOURCE_DIR}")
add_executable(hello ${PROJECT_SOURCE_DIR}/test.cpp)

# To build the project
$ cmake -H. -Bbuild # creates configuration file under build directory
$ cmake --build build -- -j3 # generate the binary for the project
  

