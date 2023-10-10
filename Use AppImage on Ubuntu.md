# How to use AppImage on Ubuntu

## install FUSE
    
```bash
sudo apt install fuse libfuse2
```

## install AppImageLauncher

```bash
sudo add-apt-repository ppa:appimagelauncher-team/stable
sudo apt update
sudo apt install appimagelauncher
```

## install AppImage

```bash
chmod +x <app>.AppImage
./<app>.AppImage
```

## add AppImage to application menu

```bash
appimagelauncher-installer <app>.AppImage
```

## add AppImage to startup applications

```bash
appimagelauncher-configuration
```

## add AppImage to desktop

```bash
appimagelauncher-register <app>.AppImage
```

## remove AppImage from desktop

```bash
appimagelauncher-unregister <app>.AppImage
```

## remove AppImage from application menu

```bash
appimagelauncher-uninstaller <app>.AppImage
```

## remove AppImage from startup applications

```bash
appimagelauncher-configuration
```

## Reference
[How to Use AppImage on Ubuntu](https://www.itprotoday.com/development-techniques-and-management/why-and-how-use-appimage-ubuntu)