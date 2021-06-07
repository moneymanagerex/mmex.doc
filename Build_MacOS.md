Building Money Manager Ex from sources
======================================

macOS with Homebrew
-------------------

### 1. Install Prerequisites

1. First verify, if you have installed *Xcode Command Line Tools*. Open
   terminal and type `git --version` if it shows something like
   `git version 2.11.0 (Apple Git-81)`
   you are fine. If not, you will be prompted to *Install* them via your
   operating system. Alternatively, you can install those tools via command:

       xcode-select --install

2. After that, for comfortable installing software we use [Homebrew].
   Run the command:

       /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

3. Install required packages. You can choose which compiler you want to use:

       brew update && brew install ccache gettext cmake
       brew link --force gettext

### 2. Build wxWidgets

The wxmac stable version with homebrew is still 3.0.5.x, we need a later version so need to build wxWidgets from source

1. Download Sources
        
        /bin/bash -c "$(curl -fsSL -O https://github.com/wxWidgets/wxWidgets/releases/download/v3.1.5/wxWidgets-3.1.5.tar.bz2)"
        tar xzf wxWidgets-*.tar.bz2

2. Build from source

        cd wxWidgets-3.1.5
        mkdir build-cocoa
        cd build-cocoa
        export MAKEFLAGS=-j4
        ../configure --disable-shared --enable-cxx11 --with-cxx=11 \
        --with-macosx-version-min=10.14 \
        --without-libtiff
        --enable-universal-binary=arm64,x86_64

    If you want to enable debug then include `--enable-debug`

    If you want to just build for the current architecture and don't require a universal build then you can omit `--enable-universal-binary=arm64,x86_64`

    You could tune `-j4` option to different number to use all processor cores during build phase.


### 2. Download Sources

    git clone --recursive https://github.com/moneymanagerex/moneymanagerex

### 3. Compile and Create Package

    mkdir moneymanagerex/build
    cd moneymanagerex/build
    export MAKEFLAGS=-j8
    cmake -DCMAKE_CXX_FLAGS="-w" \
    -DwxWidgets_CONFIG_EXECUTABLE={PATH-TO-wxWidgets}/wxWidgets-3.1.5/build-cocoa/wx-config \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_OSX_ARCHITECTURES="arm64;x86_64" \
    -DMACOSX_DEPLOYMENT_TARGET=10.14 \
    --with-macosx-version-min=10.14 ..
    cmake --build .. --target package

Replace `{PATH-TO-wxWidgets}` with the path to the directory in which you extracted the wxWidgets source in step 2.

If you want build the project for debugging purposes replace CMake flag
`-DCMAKE_BUILD_TYPE=Release` with `-DCMAKE_BUILD_TYPE=Debug`.

If you want to just build for the current architecture and don't require a universal build then you can omit `-DCMAKE_OSX_ARCHITECTURES="arm64;x86_64"`

You could tune `-j4` option to different number to use all processor cores
during build phase.
   
[Homebrew]:
    https://brew.sh