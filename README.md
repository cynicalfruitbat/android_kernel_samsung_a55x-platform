# How to build

## 1. Import the toolchain
```shell
repo init -u https://github.com/cynicalfruitbat/android_kernel_samsung_a55x-manifest -b android14-6.1
repo sync -c --no-tags --no-clone-bundle -j$(nproc --all)
```

## 2. Initialise the submodule (Kernel)
```shell
cd kernel_platform
git submodule init
git submodule update
```

## 3. Initiate the build
```shell
tools/bazel run --nocheck_bzl_visibility --config=stamp --sandbox_debug --verbose_failures --debug_make_verbosity=I //projects/s5e8845:s5e8845_user_dist
```

Produced files can be found in out/s5e8845_user/dist
