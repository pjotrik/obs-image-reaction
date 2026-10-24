# OBS Image Reaction Plugin
Image that reacts to sound source.

## Installing binaries
Download the latest version from [releases](https://github.com/pjotrik/obs-image-reaction/releases).

### Windows (OBS 30 or newer)
1. Close OBS.
2. Extract the `windows-x64` zip.
3. Move the `libimage-reaction` folder into `C:\ProgramData\obs-studio\plugins\` (create the `plugins` folder if it does not exist).

You should end up with `C:\ProgramData\obs-studio\plugins\libimage-reaction\bin\64bit\libimage-reaction.dll`.

### GNU/Linux
There is no prebuilt Linux package yet. This plugin needs OBS 33 or newer; build it from source (see below).

### Mac OS
Try this port from ashmanix: https://github.com/ashmanix/obs-image-reaction .

## Building and installing for GNU/Linux:
```
git clone https://github.com/pjotrik/obs-image-reaction
cd obs-image-reaction
mkdir build
cd build
cmake ..
make
mkdir -p ~/.config/obs-studio/plugins/libimage-reaction/bin/64bit
cp libimage-reaction.so ~/.config/obs-studio/plugins/libimage-reaction/bin/64bit/
cp -r ../data  ~/.config/obs-studio/plugins/libimage-reaction/
```

## Building for Windows from GNU/Linux:
You need to download MinGW, OBS Studio source code, Wine, install OBS Studio using wine.
```
git clone https://github.com/pjotrik/obs-image-reaction
cd obs-image-reaction
mkdir build-win
cd build-win
cmake ..  -DCMAKE_SYSTEM_NAME=Windows  -DCMAKE_CXX_COMPILER=/usr/bin/x86_64-w64-mingw32-g++-win32  -DCMAKE_C_COMPILER=/usr/bin/x86_64-w64-mingw32-gcc-win32 -DLIBOBS_INCLUDE_DIR=~/git/obs-studio-27.0.1/libobs -DLIBOBS_LIB=~/.wine/drive_c/Program\ Files/obs-studio/bin/64bit/obs.dll
make
```
Now move libimage-reaction.dll into OBS Plugin directory.
