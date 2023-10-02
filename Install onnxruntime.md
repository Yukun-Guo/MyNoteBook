# Install ONNXRuntime on Linux

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

### Install ONNXRuntime

```bash
git clone --recursive https://github.com/Microsoft/onnxruntime.git
cd onnxruntime
./build.sh --config RelWithDebInfo --build_shared_lib --parallel --compile_no_warning_as_error --skip_submodule_sync
```
