# Yocto-Julia Demo Distros

> This is in development and not all aspects have been completed!

Reference/demo distribution for various embedded platforms
using Yocto Project tools and the [meta-julia](https://github.com/NickMcSweeney/meta-julia) BSP layer.

The following processors have been tested:

| Brand           | Board         | Status                                         |
| --------------------- | ---------------|---------------------------------------------------- |
| NVIDIA Jetson                  | AGX Xavier         | Can install Julia Language. GPU is functional with CUDA.jl          |
| Raspberry Pi            | Pi4 B         | Untested             |
| Pine64  | Quartz64 B         | Untested        |

## Prerequisites

See the [Yocto Project Quick Build](https://docs.yoctoproject.org/brief-yoctoprojectqs/index.html)
documentation for information on setting up your build host.

For burning SDcards, the `bmap-tools` package is recommended.

## Setting up

1. Clone this repository:

        $ git clone https://github.com/NickMcSweeney/yocto-julia-distros.git

2. Change to the appropriate sub-directory for your device.

3. Initialize the git submodules:

        $ cd nvidia-jetson
        $ git submodule update --init

4. Source the `setup-env` script to create a build directory,
   specifying the MACHINE you want to configure as the default
   for your builds. For example, to set up a build directory
   called `build` that is set up for the Jetson AGX Xavier
   developer kit and the default `juliademo` distro:

        $ . ./setup-env --machine jetson-agx-xavier-devkit

   You can get a complete list of available options, MACHINE
   names, and DISTRO names with

        $ . ./setup-env --help

5. Optional: Install pre-commit hook for commit autosigning using
        $ ./scripts-setup/setup-git-hooks

## Distributions

Use the `--distro` option with `setup-env` to specify a distribution for your build,
or customize the DISTRO setting in your `$BUILDDIR/conf/local.conf` to reference one
of the supported distributions.

Currently supported distributions are listed below:


| Distribution name | Description                                                   |
| ----------------- | ------------------------------------------------------------- |
| juliademo         | Default distro used to demonstrate/test meta-julia language install   |
| juliapkgdemo         | Default distro used to demonstrate/test meta-julia language & julia package/application install   |


# Contributing

Please see the contributor page at [this link](https://github.com/NickMcSweeney/meta-julia/blob/master/CONTRIBUTING.md).
Contributions are welcome!
