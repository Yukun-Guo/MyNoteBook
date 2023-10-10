# Install ONNXRuntime on Linux

## install from pre-built binaries

Download the *.tgz file from [here](https://github.com/microsoft/onnxruntime/releases).
Extract it.

``` bash
wget https://github.com/microsoft/onnxruntime/releases/download/v1.15.1/onnxruntime-linux-x64-gpu-1.15.1.tgz
tar -xvf onnxruntime-linux-x64-gpu-1.15.1.tgz
```

Move and include the header files in the include directory.

```bash
sudo cp -r onnxruntime-linux-x64-gpu-1.15.1/include/ /usr/local/include/onnxruntime
```

Move the libonnxruntime.so dynamic library to a desired path and include it.

```bash
sudo cp -r onnxruntime-linux-x64-gpu-1.15.1/lib /usr/local
sudo ldconfig
```

## Prerequisites

### python 3.x, pip3 and cmake-3.26 or higher

```bash
sudo apt-get update
sudo apt-get install python3-pip
python3 -m pip install --upgrade pip
python3 -m pip install cmake
which cmake # check cmake is installed
cmake --version # check cmake version
```

## Install ONNXRuntime

```bash
git clone --recursive https://github.com/Microsoft/onnxruntime.git
cd onnxruntime
./build.sh --config RelWithDebInfo --build_shared_lib --parallel --compile_no_warning_as_error --skip_submodule_sync
```

### reference

[Build ONNX Runtime for inferencing](https://onnxruntime.ai/docs/build/inferencing.html)
