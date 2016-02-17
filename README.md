# t2-test-rig-debian-live
Debian live-build configuration for test rig netbook

## Setup
First, clone and install our fork of [live-build](https://github.com/kevinmehall/live-build). Live build is a utility that takes a configuration file and generates a live build image. It is installed as the `lb` command:
```
git clone https://github.com/kevinmehall/live-build.git;
cd live-build;
make install;
```
Then, install the dependencies:
```
sudo apt-get install debootstrap
```

# Configuring

`bash config.sh` generates the initial configuration. You only need to run it once or when you change it.

# Building

`sudo lb build`

The resulting image is `live-image-i386`. You can `dd` this to a USB flash drive or SD card. It is not currently built to be burned to a CD (the targeted machines don't have optical drives).

Boot it in qemu with `qemu-system-x86_64 --enable-kvm  -hda live-image-i386 -m 1024`.

# Cleaning

`sudo lb clean` cleans temporary files. It is occasionally necessary after changing certain things.

# Links
 
 * [Debian Live manual](http://live.debian.net/manual/git/html/live-manual.en.html)
