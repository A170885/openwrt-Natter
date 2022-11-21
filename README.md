Natter on Openwrt
=================

## Introduction
This project is the software package of [Natter][] running on OpenWrt  
Recommended to use it with `luci-app-commands`

## Build

```shell
# Take the x86_64 platform as an example
tar xjf openwrt-sdk-21.02.3-x86-64_gcc-8.4.0_musl.Linux-x86_64.tar.xz
# Go to the SDK root dir
cd OpenWrt-sdk-*-x86_64_*
# First run to generate a .config file
make menuconfig
./scripts/feeds update -a
./scripts/feeds install -a
# Get Makefile
git clone --depth 1 --branch master --single-branch --no-checkout https://github.com/muink/openwrt-Natter.git package/natter
pushd package/natter
umask 022
git checkout
popd
# Select the package LuCI -> Applications -> natter
make menuconfig
# Start compiling
make package/natter/compile V=99
```

## License
This project is licensed under the [GPL-3.0](https://www.gnu.org/licenses/gpl-3.0.html)

  [Natter]: https://github.com/MikeWang000000/Natter
