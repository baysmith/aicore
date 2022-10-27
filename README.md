# About This Repository

This repository should now be considered a historical curiosity only.

The original version of this code was developed between 2002-2004 and included free with the book "Artificial Intelligence for Games". Over the intervening years, the code has become a less useful reference. The third edition of the textbook is considerably larger, and this code did not keep up with errata or improvements in the algorithms. I have not use the code in this repository for my consulting work in over a decade.

The third edition of the textbook does not mention this code, but includes considerably expanded and corrected listings in the text in a language neutral format. I would recommend that version.


---

# Historical Information

The Artificial Intelligence for Games system.

Copyright (c) Ian Millington 2003-2009. All Rights Reserved.

This software is distributed under licence. Use of this software
implies agreement with all terms and conditions of the accompanying
software licence.

This code also contains portions of the AI Core engine.

Copyright (c) Icosagon Limited 2003-2007. All Rights Reserved.

Please see accompanying LICENSE file.



Installation
============

The code can be extracted to any directory.


Platform Compatibility
======================

The software has been designed for platform indepedence as much as
possible. The only file that may need altering for your platform is
./src/timing.cpp which currently wraps the windows multimedia timer.


Building
========

Building with Conan and CMake
-------------------

The code can be built using CMake and the Conan package manager.

```shell
mkdir build
cd build
conan install ..
cmake .. -G "Visual Studio 16"
cmake --build . --config Release
```

The "Visual Studio 16" may need to be replace with another compiler. Use `conan
profile show default` to see which compiler conan is using.


Documentation
-------------

To build the documentation (see below) you must have doxygen
installed (it is available from http://www.stack.nl/~dimitri/doxygen/
Simply cd into the ./doc/build/doxygen directory, then type:

> doxygen aicore.config

to build the documentation.


Layout
======

The build process creates a statically linked library in ./lib which
can be used with the include headers in ./include. The demo programs
are built and placed in the ./bin directory.

Source code is contained in the ./src directory, and documentation
is in the ./doc directory, in particular the reference documentation
is in the ./doc/ref directory.


Documentation
=============

The source code is heavily documented, and the contents correspond to
the discussion in the "Artificial Intelligence for Games" book.

It is possible to create 'doxygen' documentation with the tags in the
source code files, and a configuration for building the documentation
is provided in the ./doc/build/doxygen directory. The doxygen
configuration supplied provides only html output, since other output
formats depend on how your machine is configured.

This is not currently targeted from the scons configuration, because
scons suport for doxygen depends on where doxygen is installed on your
machine.


Demos
=====

To run the demos you will require OpenGL and GLUT installed on your
machine, and the relevant DLLs or shared objects on the path.

