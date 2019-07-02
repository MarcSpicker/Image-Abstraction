# Image-Abstraction

This is the `cmake` branch for building the project using CMake.

# Building with CMake

You can build the software with CMake by switching to the experimental branch `cmake` and running following commands:

```bash
mkdir build
cmake -B build/
make -C build/
build/Image-Abstraction
```

### Dependencies
The following libraries are required:
* Compiler supporting C++11
* CMake 3.10
* Qt5Widgets