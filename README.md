# platform-orangepi

This repo contains platform specific files used by the Volumio Builder to create **OrangePi** images:

The kernel, modules, firmware and u-boot files are created from armbian using the mainline kernel.
There is a dtb overlay to enable the i2s0 connection for pcm5102a audio devices.

Currently supported OrangePi devices are
* OrangePi One
* OrangePi Lite
* OrangePi PC

## Kernel Sources
Kernel sources ar from `git://git.kernel.org/pub/scm/linux/kernel/git/stable/linux-stable.git` branch `linux-4.19.y`

Firmware sources are from `https://github.com/armbian/firmware` branch `master`

U-Boot sources are from `git://git.denx.de/u-boot.git` the `2017.11` tag

## Creating/Updating a platform archive

Clone the armbian repository as a sibling to this directory
```bash
git clone https://github.com/armbian/build ../armbian
./mkplatform.sh lite
```

## Changelog

12 Mar 21
- add patch for wm8804.c driver to make it work in software mode  as master. TESTED
- add dts file for aliexpress pifi wm8804 hat.
  |- in dts file disabled internal HDMI audio to make tests easier , not to confuse outputs.
- TESTED with kernel 5.10. 


24 Jan 19
- update to armbian build 4.19.17

18 Apr 18
- Update to armbian build with kernel 4.14.34
