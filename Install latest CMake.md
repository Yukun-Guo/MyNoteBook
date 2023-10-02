# Ubuntu install latest version of CMake

## Install CMake from Ubuntu repository

```bash
sudo apt-get update
sudo apt-get install cmake
```

## Install CMake from source

### Configure the VPSie cloud server

```bash
apt-get update && apt-get upgrade -y
```

### Install build tools and libraries

```bash
sudo apt-get install build-essential libssl-dev
```

### install CMake

```bash
version=3.27
build=1
cd/tmp
wget https://cmake.org/files/v$version/cmake-$version.$build.tar.gz
tar -xzvf cmake-$version.$build.tar.gz
cd cmake-$version.$build/
./bootstrap
make -j7
sudo make install
```

### Verify the installation

```bash
cmake --version
```

#### reference

[Install The Latest CMake Version in Ubuntu 18.04 (Bionic Beaver)](https://milicendev.netlify.app/article/install-the-latest-cmake-version-in-ubuntu-18-04-bionic/)
[How do I install the latest version of cmake from the command line](https://askubuntu.com/questions/355565/how-do-i-install-the-latest-version-of-cmake-from-the-command-line)