# Valgrind Exercise

# What happens when the executable is linked statically?  Does Valgrind still detect those same bugs?
When an executable is linked statically rather than dynamically, valgrind can still detect the memory related bugs like leaks, uninitialized memory. In static linking, since all necessary libraries are included in the binary, Valgrind can still analyze the program. However, it may be more difficult to track the origin of certain bugs. In static linking, the code from the libraries is merged with the executable, which can make it harder to pinpoint issues arising from them and the analysis may take longer due to the larger executable size.

## Standard install via command-line
```bash
# Configure the project and generate a native build system:
  # Must re-run this command whenever any CMakeLists.txt file has been changed.
  cmake -S ./ -B build/
# To build with debugging information, do:
  cmake -S ./ -B build/ -D CMAKE_BUILD_TYPE=Debug
# Compile and build the project:
  # rebuild only files that are modified since the last build
  cmake --build build/
  # or rebuild everything from scracth
  cmake --build build/ --clean-first
  # to see verbose output, do:
  cmake --build build/ --verbose
# Run program:
  ./build/app/shell-app
# Clean
  cmake --build build/ --target clean
# Clean and start over:
  rm -rf build/
```

