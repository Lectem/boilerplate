# C++/CMake modern boilerplate
[![Travis build Status](https://travis-ci.org/Lectem/cpp-boilerplate.svg?branch=master)](https://travis-ci.org/Lectem/cpp-boilerplate)
[![Appveyor build status](https://ci.appveyor.com/api/projects/status/63mnrl1am9plfc4f/branch/master?svg=true)](https://ci.appveyor.com/project/Lectem/boilerplate/branch/master)
[![Coverage](https://codecov.io/gh/Lectem/cpp-boilerplate/branch/master/graph/badge.svg)](https://codecov.io/gh/Lectem/cpp-boilerplate)
[![CDash dashboard](https://img.shields.io/badge/CDash-Access-blue.svg)](http://my.cdash.org/index.php?project=cpp-boilerplate)
[![Pull requests](https://img.shields.io/github/issues-pr-raw/Lectem/cpp-boilerplate.svg)](https://github.com/Lectem/cpp-boilerplate/pulls)
[![Opened issues](https://img.shields.io/github/issues-raw/Lectem/cpp-boilerplate.svg)](https://github.com/Lectem/cpp-boilerplate/issues)

This is a template for new projects, gives a good CMake base and a few dependencies you most likely want in your project. It also set ups some basic CI builds.
It uses "modern" CMake, ie 3.x paradigms, and should be a good starting point for both people willing to learn it and those that want to update/upgrade their CMakeLists.txt !
If you disagree with some pieces of advice given here, please discuss it with me by opening a Github Issue ! Enhancements are always welcome.

## Usage

If you want to bootstrap a new project you only need to :

 * If you don't already have your git repository setup
   - Simply copy/paste the folder (without the .git folder) and run the .bat file (renaming to .sh should work for linux). This will create an initial git commit and add the *required* submodules.
 * Hack CMakeLists.txt and CTestConfig.cmake to change the project name
 * Ready to go !

The CI providers used and that might need some setup :

 * Travis CI, for GCC / Clang on Linux/MacOS
 * AppVeyor, for MSVC on Windows
 * Codecov.io, for the codecoverage reports
 * CDash, for test and coverage reports using CTest. Can also be used to build nightlies.

## Requirements :

 * CMake 3.8.2 (Not needed for all scripts)
 * Git (for the submodules)
 * Any of the CI providers listed above if needed.

## Some features/notes :

 * Scripts lying in the cmake/ folder can be copy/pasted for use in any CMake project
 * Uses c++14
 * RunFixupBundle.cmake script : A small wrapper around fixup_bundle
 * LTO.cmake script : Easier link time optimization configuration (should work on all CMake 3.x versions) as it used to be painful to setup.
 * Warnings.cmake script : A wrapper around common warning settings
 * Basic unit-testing using [doctest](https://github.com/onqtam/doctest)
 * Coverage.cmake : Test coverage script to add a 'Coverage' build type to CMake

## External dependencies (using submodules)

Those dependencies can be easily removed by changing the external/CMakelists.txt and cleaning main.cpp.

 * [libfmt](https://github.com/fmtlib/fmt) In my opinion the best formating library
 * [spdlog](https://github.com/gabime/spdlog) A logging library based on libfmt
 * [doctest](https://github.com/onqtam/doctest) A test library not as heavy as the others
