Flymake for the CMake build system
==================================

These are python scripts for using the [CMake build system](http://www.cmake.org/) with [Flymake](http://flymake.sourceforge.net/), an on-the-fly syntax checker for GNU Emacs. I've found these [scripts](https://github.com/seanfisk/cmake-flymake) written by Sean Fisk. But it didn't work for me because some relative path issue. So I re-write it in python.

Dependencies
------------

These scripts require a few obvious dependencies.

* [Emacs 23](http://www.gnu.org/software/emacs/), which includes Flymake (this is not necessary to run the script, but to use the results)
* [Python](http://www.python.org/software/bash/), I tested it with python 2.7 but I think 2.2 will be fine.
* [CMake](http://www.cmake.org/), I tested it with cmake 2.8

Installation
------------

	All you need is the script `cmflymk`. Download it at https://github.com/redguardtoo/pycmake-flymake.

Usage
---

1. Create Makefiles for flymake in one step (Make sure you've run cmake under ~/your_project/cmake_project_build/ at first)
        cmflymk ~/your_project/cmake_project_build/ 
	
2. `M-x flymake-mode` in Emacs
3. DONE!

Other Notes
-----------

* When you change any of your `CMakeLists.txt` files, re-run `cmake` and `cmflymk`.
* To remove the Flymake Makefiles, run `cmflymk -c`.
* These scripts are configured to use the GNU make variables ${CXX}, ${CXX\_FLAGS}, and ${CXX\_DEFINES} in the actual Makefiles. This means that the scripts will require editing to work with pure C projects (when using CC, CFLAGS, etc.) or any other language besides C++. This should be quite easy to figure out. Look at the actual Makefiles which get generated for more information.
* I haven't tested this on Windows because I'm only working under Linux/Cygwin. Contact me (chenbin DOT sh AT GMAIL) if you need Windows support.

