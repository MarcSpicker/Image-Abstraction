# Image-Abstraction
The code depends only on Qt4.

To compile it 

```bash

cd ~/ImageAbstractionInterface
qmake 
make 
./image_abstraction 
```

# Building with CMake

You can build the software with CMake by switching to the experimental branch `cmake` and running following commands:

```bash
mkdir build
cmake -B build/
make -C build/
build/Image-Abstraction
```

Only dependency here is *Qt5Widgets*.