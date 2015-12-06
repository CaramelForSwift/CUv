CUv
-

A module for libuv in pure Swift applications. This module was built for the use of the [Caramel framework](https://github.com/CaramelForSwift/Caramel.git).

Installation
-

First, you must build and install libuv. This package assumes libuv is installed to "/usr", so we'll install it here.

1. Clone [libuv](https://github.com/libuv/libuv.git)
2. Check out to the tag you want (this build assumes a minimum of `v1.7.5`)
3. `cd libuv`
4. `sh autogen.sh`
5. `./configure --prefix=/usr`
6. `make install` (with `sudo` as needed)

Usage
-

Add this to your `Package.swift` file:

```swift
import PackageDescription

let package = Package(
    dependencies: [
        .Package(url: "https://github.com/CaramelForSwift/CUv.git", majorVersion: 1)
    ]
)
```

Then you can import the module and use `libuv` functions like so:

```swift
import CUv

let loop = uv_default_loop()
uv_run(loop, UV_RUN_DEFAULT)
print("Event loop: \(loop)")
```

License
-

Written by Steve Streza.

This package is released into the public domain. Any license provided by `libuv` are still applicable.

