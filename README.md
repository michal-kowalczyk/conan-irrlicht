[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg?maxAge=3600)](https://raw.githubusercontent.com/mpusz/conan-irrlicht/master/LICENSE)
[![Travis CI](https://img.shields.io/travis/mpusz/conan-irrlicht/master.svg?label=Travis%20CI)](https://travis-ci.org/mpusz/conan-irrlicht)
[![AppVeyor](https://img.shields.io/appveyor/ci/mpusz/conan-irrlicht/master.svg?label=AppVeyor)](https://ci.appveyor.com/project/mpusz/conan-irrlicht)
[![Download](https://api.bintray.com/packages/mpusz/conan-mpusz/irrlicht%3Ampusz/images/download.svg)](https://bintray.com/mpusz/conan-mpusz/irrlicht%3Ampusz/_latestVersion)

# conan-irrlicht

[conan-mpusz](https://bintray.com/mpusz/conan-mpusz) package for [Irrlicht](http://irrlicht.sourceforge.net/) library.

The package generated with this **conanfile** can be found at [conan-mpusz](https://bintray.com/mpusz/conan-mpusz/irrlicht%3Ampusz).

`conan` client can be downloaded from [Conan.io](https://conan.io).

## Use the package

### Add the remote

To add [conan-mpusz](https://bintray.com/mpusz/conan-mpusz) remote to your
local `conan` instance run:

```bash
$ conan remote add conan-mpusz https://api.bintray.com/conan/mpusz/conan-mpusz
```

### Basic setup

```bash
$ conan install irrlicht/1.8.4@mpusz/stable -pr <your_conan_profile> -b=outdated
```

### Project setup

If you handle multiple dependencies in your project, it would be better
to add a `conanfile.txt`

```
[requires]
irrlicht/1.8.4@mpusz/stable

[generators]
cmake
```

or if you are using `conanfile.py` file add:

```python
requires = "irrlicht/1.8.4@mpusz/stable"
```

Complete the installation of dependencies for your project by running:

```bash
$ mkdir build
$ cd build
$ conan install .. -b=outdated <your_profile_and_settings>
< your typical build process>
```

Project setup installs the library (and all its dependencies), and assuming you chose
`cmake` as a generator, it generates `conanbuildinfo.cmake` file that defines variables
to make CMake work and find all the dependencies in the Conan local cache.

## Available Options

| Option | Default | Values        | Description                         |
|--------|---------|---------------|-------------------------------------|
| shared | False   | [True, False] | Generates shared library            |
| fPIC   | True    | [True, False] | Generates position-independent code |

## Build package

```bash
$ conan create . <user>/<channel> <your_profile_and_settings>
```

## Upload package to server

```bash
$ conan upload -r <remote-name> --all irrlicht/1.8.4@<user>/<channel>
```
