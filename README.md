[![build](https://github.com/floooh/sokol-nim/actions/workflows/main.yml/badge.svg)](https://github.com/floooh/sokol-nim/actions/workflows/main.yml)

Auto-generated Nim bindings for the [sokol headers](https://github.com/floooh/sokol).

## Build and run samples

First install sokol as local module:

```sh
nimble install
```
Remember to do this each time you update the bindings.

Then to build and run the samples with the platform's default 3D backend
(D3D11 on Windows, Metal on macOS, GL on Linux):

```sh
nimble clear
nimble triangle
nimble quad
nimble bufferoffsets
nimble cube
nimble noninterleaved
nimble texcube
nimble shapes
nimble offscreen
nimble instancing
nimble mrt
nimble blend
nimble debugtext
nimble debugtextprintf
nimble debugtextuserfont
nimble sgl
nimble sglcontext
nimble sglpoints
nimble saudio
```

To force the GL backend (on Windows or Mac) use ```-d:gl``` before the target:

```sh
nimble -d:gl clear
```

To build all samples into the ```build/``` subdirectory:

```sh
# with debug info
nimble build_debug
# in release mode:
nimble build_all
# ...or with forced GL backend:
nimble -d:gl build_debug
nimble -d:gl build_all
```


## Tested platform/compiler combinations

* Windows, Nim 1.4.4
  ```sh
  # clang 11.0.1
  nim c --cc:clang

  # gcc 6.3.0
  nim c --cc:gcc

  # Microsoft cl 19.28.29336
  nim c --cc:vcc
  ```
* Linux, Nim 1.4.4
  ```sh
  # clang 10.0.0
  nim c --cc:clang

  # gcc 7.5.0
  nim c --cc:gcc
  ```

* Apple, Nim 1.4.4
  ```
  Nim Compiler Version 1.4.4 [MacOSX: amd64]
  ```

## Examples

Examples are found in the `examples` subdirectory, and can be compiled and run as follows:

```sh
# install sokol
$ cd path/to/sokol-nim
$ nimble install

# compile & run cube.nim using the platform's
# native graphics API
$ nim c --run examples/cube.nim

# compile & run cube.nim using OpenGL or OpenGL ES
# explicitly (-d:gl)
$ nim c --run -d:gl examples/cube.nim
```
