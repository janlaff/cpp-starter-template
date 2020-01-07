# Modern c++20 starter template using Hunter

This project uses hunter as a package manager

See https://github.com/ruslo/hunter

And catch2 as unit testing library

See https://github.com/catchorg/Catch2

## Project Structure
### `CMakeLists.txt`
General project configuration, Libraries

Set Project name here, or use shell script to automatically do that

### `include/`
Contains `*.h` header files

### `src/`
Contains `*.cpp` source files

### `test/`
Contains `*.test.cpp` Catch2 unit test files

### `cmake/`
Contains HunterGate

### `scripts/`
Contains new project creation script that can be added to your shell path to quickly generate new c++ projects

You don't need to install this shell script, you could also just change the project name of this project in `CMakeLists.txt` and start from this

###### Example (Assuming script dir is in path):
`$ new-cpp-project ExampleProject`

This creates a new cmake project    

## Cmake Output
* Library (eg ExampleProject-lib)
* Executable (eg ExampleProject)
* Unit tests (eg ExampleProject-test)

## IDE
I recommend using a CMake-based IDE like CLion from Jetbrains or similiar products to automatically build and run this project
