# Almost all CMake files should start with this
# You should always specify a range with the newest
# and oldest tested versions of CMake. This will ensure
# you pick up the best policies.
cmake_minimum_required(VERSION 3.16...3.27)

# This is your project statement. You should always list languages;
# Listing the version is nice here since it sets lots of useful variables
project(
    polarcodes
    VERSION 0.1
    LANGUAGES CXX)

# If you set any CMAKE_ variables, that can go here.
# (But usually don't do this, except maybe for C++ standard)

# Find packages go here.

# You should usually split this into folders, but this is a simple example

# This is a "default" library, and will match the *** variable setting.
# Other common choices are STATIC, SHARED, and MODULE
# Including header files here helps IDEs but is not required.
# Output libname matches target name, with the usual extensions on your system
# add_library(MyLibExample simple_lib.cpp simple_lib.hpp)

# Link each target with other targets or add options, etc.

# Adding something we can run - Output name matches target name
add_executable(
    polarcodes
    testpolar.cc
    polarcode.cc
    polarcode.h
    matalloc.h
    polarstack.h
    printstuff.cc
    bittype.h
    quicksortstuff.cc
    randstuff.cc
)

# target_include_directories adds an include directory to a target. PUBLICdoesn't
# mean much for an executable; for a library it lets CMake know that any targets
# that link to this target must also need that include directory. Other options
# are PRIVATE (only affect the current target, not dependencies), and INTERFACE
# (only needed for dependencies).
target_include_directories(polarcodes PUBLIC .)

# Make sure you link your targets with this command. It can also link libraries and
# even flags, so linking a target that does not exist will not give a configure-time error.
# target_link_libraries(MyExample PRIVATE MyLibExample)

# # [main]

# This part is so the Modern CMake book can verify this example builds. For your code,
# you'll probably want tests too
# enable_testing()
# add_test(NAME MyExample COMMAND MyExample)
