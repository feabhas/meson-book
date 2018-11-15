# Why try Meson?

Perception: Meson is very similar to scons \(python based build\) but seems to have the following advantages:

* It’s actively being worked on and maintained. 
* Scons doesn’t appear to have any updates in a couple of years
* It’s significantly faster than scons \(not an issue for us, but maybe for our clients\)
* It’s a modern build system which the community seem to be referencing alongside Cmake, make and autotools \(where scons is never mentined\).
* It appears to have a “cross-compile” config \(examples even for Arduino\)
* It uses a similar concept to the main build file and separate build files in each directory, but on the surface looks easier than the SConscript model. 
* 
See if these arguments stand up to experimentation...

The main usability difference between Ninja and Make is that Ninja will automatically detect the number of CPUs in your computer and parallelize itself accordingly.

Meson follows the overall structure of other popular build systems, such as CMake and GNU Autotools. This means that the build is divided into two discrete steps: configure step \_and \_build step

.The first step inspects the system, checks for dependencies and does all other steps necessary to configure the build. It then generates the actual build system.

The second step is simply executing this generated build system. The end result is a bunch of build targets, which are usually executables and shared and static libraries.



