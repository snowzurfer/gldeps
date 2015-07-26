# gldeps - One stop OpenGL app dependencies

The gldeps project aims to act as a one stop shop to quickly set up OpenGL
projects.

## Libraries

* [glfw](https://github.com/glfw/glfw/releases/tag/3.1.1)
* [gl3w](https://github.com/skaslev/gl3w/commit/8c727cd02803aa05783abc56eb212fb26d4c205d) + generated source files
* [glm](https://github.com/g-truc/glm/releases/tag/0.9.6.3)
* [imgui](https://github.com/ocornut/imgui/releases/tag/v1.43)

## Usage

To include gldeps into your project it is recommended to include the repository
into your own, either using git submodule.

```
git submodule add https://github.com/kbenzie/gldeps.git <path/to/gldeps>
```

Or git subtree.

```
git subtree add --squash -P <path/to/gldeps> https://github.com/kbenzie/gldeps.git master
```

Integration into an existing CMakeLists.txt is performed by adding gldeps as a
sub directory, then there are two CMake variables; `GLDEPS_INCLUDE_DIRS`
contains a list of paths to required headers; and `GLDEPS_LIBRARIES` which
contains a list of libraries to link against.

```cmake
add_subdirectory(<path/to/gldeps>)
include_directories(${GLDEPS_INCLUDE_DIRS})
...
target_link_libraries(<target> ${GLDEPS_LIBRARIES})
```
