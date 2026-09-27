# C++ Project Template

This is a simple C++ project created to be a base for modern 
C++ projects I want to play around with. This is not a full
project itself. Here is what it has:

- CMake support for building the project
- C++ 26 support. Clang has less features implmented than GCC but I don't need them
- [VCPKG](https://vcpkg.io/en/) for package management, make sure it's [installed first](https://learn.microsoft.com/en-us/vcpkg/get_started/get-started?pivots=shell-bash)
- built to support using clangd in modern text editors (formatting, tidy, compile commands)
- [Zed editor](https://zed.dev/) configuration so I can run and debug in Zed (my favourite text editor)
- a simple `.gitignore`

Build, download and create all the metadata files needed for clangd

```sh
cmake --preset debug
cmake --build --preset debug
```

Run the application:

```sh
./build/debug/myapp
```

Example application is from [learncpp.com](https://www.learncpp.com/cpp-tutorial/what-language-standard-is-my-compiler-using/)
