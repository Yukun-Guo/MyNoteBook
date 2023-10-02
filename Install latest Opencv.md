# install lateste version of OpenCV

## Install OpenCV from Ubuntu repository

```bash
sudo apt-get update
sudo apt-get install libopencv-dev python-opencv
dpkg -l libopencv-dev # check the version
```


## Install OpenCV from source

### Access the command line and update the Ubuntu packages list

```bash
sudo apt-get update
```

###  Install developer tools, image and video libraries, and other dependencies necessary to build OpenCV

```bash
sudo apt install build-essential cmake git libgtk-3-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev libv4l-dev libxvidcore-dev libx264-dev openexr libatlas-base-dev libopenexr-dev libgstreamer-plugins-base1.0-dev libgstreamer1.0-dev python3-dev python3-numpy libtbb2 libtbb-dev libjpeg-dev libpng-dev libtiff-dev libdc1394-dev gfortran -y
```

### Create and access a directory for the OpenCV build. In this example, the directory is called

```bash
mkdir ~/opencv_build && cd ~/opencv_build
```

### Download the OpenCV source code

```bash
git clone https://github.com/opencv/opencv.git
```

### Download the OpenCV contrib source code

```bash
git clone https://github.com/opencv/opencv_contrib.git
```

### Create the build directory within the opencv directory and access it

```bash
mkdir -p ~/opencv_build/opencv/build && cd ~/opencv_build/opencv/build
```

### Configure the build using cmake, and include the path to the cloned extra modules

```bash
cmake -D CMAKE_BUILD_TYPE=Release -D CMAKE_INSTALL_PREFIX=/usr/local -D INSTALL_C_EXAMPLES=ON -D INSTALL_PYTHON_EXAMPLES=ON -D OPENCV_GENERATE_PKGCONFIG=ON -D BUILD_EXAMPLES=ON -D OPENCV_EXTRA_MODULES_PATH=~/opencv_build/opencv_contrib/modules ..
```

###  Use the make command to build OpenCV

```bash
make -j7
```

### Install OpenCV

```bash
sudo make install
```

### Verify the installation

```bash
pkg-config --modversion opencv4
```

#### References

[How to Install OpenCV on Ubuntu](https://phoenixnap.com/kb/installing-opencv-on-ubuntu)

[Installation in Linux — OpenCV](https://docs.opencv.org/4.x/d7/d9f/tutorial_linux_install.html)
