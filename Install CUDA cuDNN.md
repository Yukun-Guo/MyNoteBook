# Install CUDA and cuDNN on Ubuntu

## cuda 11.8

```bash
wget https://developer.download.nvidia.com/compute/cuda/11.8.0/local_installers/cuda_11.8.0_520.61.05_linux.run
sudo sh cuda_11.8.0_520.61.05_linux.run
sudo ldconfig
```


## [cuDnn ](https://developer.nvidia.com/cudnn)

### [Download cuDNN](https://developer.nvidia.com/rdp/cudnn-download)
Login to Nvidia and dowload Local Installer for Ubuntu18.04 x86_64 (Deb) `cudnn-local-repo-ubuntu1804-8.9.5.29_1.0-1_amd64.deb`

### Enable the local reopsitory

```bash
sudo dpkg -i cudnn-local-repo-ubuntu1804-8.9.5.29_1.0-1_amd64.deb
sudo cp /var/cudnn-local-repo-ubuntu1804-8.9.5.29/cudnn-local-E7DF3AF8-keyring.gpg /usr/share/keyrings/
# sudo apt-key add /var/cuda-repo-ubuntu2004-8-9-local/7fa2af80.pub
sudo apt-get update
```

### Install the runtime library

```bash
sudo apt-get install libcudnn8=8.9.5.29-1+cuda11.8
```

### Install the developer library (optional)

```bash
sudo apt-get install libcudnn8-dev=8.9.5.29-1+cuda11.8
```

### Install the code samples and the cuDNN library documentation (optional)

```bash
sudo apt-get install libcudnn8-doc=8.9.5.29-1+cuda11.8
```
