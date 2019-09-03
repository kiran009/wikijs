---
title: CMake
description: CMake
published: true
date: 2019-09-03T09:44:11.661Z
tags: 
---

# CMake
- CMake is an open-source, cross-platform family of tools designed to build, test and package software.
- CMake is used to control the software compilation process using simple platform and compiler independent configuration files, and generate native makefiles and workspaces that can be used in the compiler environment of your choice. 
- Simple configuration files placed in each source directory (called CMakeLists.txt files) are used to generate standard build files (e.g., makefiles on Unix and projects/workspaces in Windows MSVC) which are used in the usual way.
- CMake can generate a native build environment that will compile source code, create libraries, generate wrappers and build executables in arbitrary combinations. 
- CMake supports in-place and out-of-place builds, and can therefore support multiple builds from a single source tree.
- CMake also supports static and dynamic library builds. Another nice feature of CMake is that it generates a cache file that is designed to be used with a graphical editor. 

For example, when CMake runs, it locates include files, libraries, and executables, and may encounter optional build directives. This information is gathered into the cache, which may be changed by the user prior to the generation of the native build files.

## CMake Vs Make
Make would parse the configuration file(Makefile) containing all commands to build an artifact

In the other hand, CMake will also parse a configuration file (CMakeLists.txt), but instead of directly build the artifact, it’ll generate another configuration file that will, in fact, build the artifact.

The extra level of indirection helps to resolve the ability to create different configuration files to build your project for different platforms, thus making it portable.
![CMake](https://github.com/kiran009/cmakeTesting/blob/master/resources/cmake-environment.png)

## Advantages
[Build With Confidence](https://www.kitware.com/build-with-cmake-build-with-confidence/)
## Installation in REDHAT
- yum install cmake
## Sample project code
- https://github.com/kiran009/cmakeTesting
## To build the project
1. $ cmake -H. -Bbuild # creates configuration file under build directory
2. $ cmake --build build -- -j3 # generate the binary for the project
## Generates the executable
### ./bin/main
For Testing CMake
## With Jenkins
https://wiki.jenkins.io/display/JENKINS/CMake+Plugin
compatible with Jenkins Pipeline
- Jenkinsfile
## References
[CMake](https://cmake.org/)