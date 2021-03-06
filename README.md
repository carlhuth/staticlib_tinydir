tinydir library wrapper for Staticlibs
======================================

This project is a part of [Staticlibs](http://staticlibs.net/).

This library implements filesystem directory reading operations,
it is built on top of [tinydir](https://github.com/cxong/tinydir) library.

Link to the [API documentation](http://staticlibs.github.io/staticlib_tinydir/docs/html/namespacestaticlib_1_1tinydir.html).

Usage example
-------------

List directory:

    auto vec = staticlib::tinydir::list_directory("path/to/dir/");
    for (auto& el : vec) {
        std::cout << el.get_name() << std::endl;
        std::cout << el.get_path() << std::endl;
        std::cout << el.is_directory() << std::endl;
        std::cout << el.is_regular_file() << std::endl;
    }

How to build
------------

[CMake](http://cmake.org/) is required for building.

[pkg-config](http://www.freedesktop.org/wiki/Software/pkg-config/) utility is used for dependency management.
For Windows users ready-to-use binary version of `pkg-config` can be obtained from [tools_windows_pkgconfig](https://github.com/staticlibs/tools_windows_pkgconfig) repository.
See [StaticlibPkgConfig](https://github.com/staticlibs/wiki/wiki/StaticlibPkgConfig) for Staticlibs-specific details about `pkg-config` usage.

To build the library on Windows using Visual Studio 2013 Express run the following commands using
Visual Studio development command prompt 
(`C:\Program Files (x86)\Microsoft Visual Studio 12.0\Common7\Tools\Shortcuts\VS2013 x86 Native Tools Command Prompt`):

    git clone https://github.com/staticlibs/staticlib_config.git
    git clone https://github.com/staticlibs/staticlib_utils.git
    git clone https://github.com/staticlibs/staticlib_pimpl.git
    git clone --recursive https://github.com/staticlibs/staticlib_tinydir.git
    cd staticlib_tinydir
    mkdir build
    cd build
    cmake ..
    msbuild staticlib_tinydir.sln

See [StaticlibsToolchains](https://github.com/staticlibs/wiki/wiki/StaticlibsToolchains) for 
more information about the toolchain setup and cross-compilation.

License information
-------------------

This project is released under the [Apache License 2.0](http://www.apache.org/licenses/LICENSE-2.0).

Changelog
---------

**2016-09-06**

 * version 1.0
 * initial public version
