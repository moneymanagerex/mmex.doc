Building Money Manager Ex from sources
======================================

Microsoft Windows 10 64-bit
-----------------

### Prerequisites

1. Install free [Microsoft Visual Studio] Community 2017. Select following
   components during install:
   * Windows: Desktop development with C++
     * Visual Studio Core Editor
     * Desktop development with C++ options
       * VC++ 2017 v141 toolset (x86,x64)
       * Windows 10 SDK (10.0.x.x) for Desktop C++ x86 and x64
       * Visual C++ tools for CMake

2. Download and install [gettext pre-compiled binaries] with default options.
3. Download [wxWidgets 3.x binaries]:
   - `wxWidgets-3.*.*_Headers.7z`
   - one of `wxMSW-3.*.*-vc141_Dev.7z` or `wxMSW-3.*.*-vc141_x64_Dev.7z`
   - one of `wxMSW-3.*.*-vc141_ReleaseDLL.7z`
     or `wxMSW-3.*.*-vc141_x64_ReleaseDLL.7z`
 Unpack archives to `c:\wxWidgets\`.
 then `wxwin` environment variable must be set:
 setx wxwin c:\wxWidgets\
 
4. Start the following command from start menu:
       ```%comspec% /k "%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvarsall.bat" amd64```
       
5. Clone [MMEX official Git repository] with submodules using command-line:

       git clone --recursive https://github.com/moneymanagerex/moneymanagerex c:\Dev\
6. [Download sources of curl], ver. 7.71.1 unpack them to `c:\libcurl` and build [libcurl]
   library with following commands:
   
       mkdir c:\libcurl\build
       cd c:\libcurl\build
       set "PATH=%PATH%;%DevEnvDir%CommonExtensions\Microsoft\CMake\CMake\bin"
       cmake -G "Visual Studio 15 2017 Win64" -DBUILD_CURL_EXE=OFF -DHTTP_ONLY=ON ^
       -DENABLE_MANUAL=OFF -DBUILD_TESTING=OFF -DCURL_STATICLIB=ON ^
       -DCMAKE_USE_WINSSL=ON -DCMAKE_INSTALL_PREFIX=c:\libcurl ..
       set "CL=/MP"
       cmake --build . --target install --config Release --clean-first ^
         -- /maxcpucount /verbosity:minimal /nologo /p:PreferredToolArchitecture=x64
         
    ### Visual Studio GUI with project file
    
    1. Generate build environment using [CMake]

       ```mkdir c:\dev\moneymanagerex\build
       cd c:\dev\moneymanagerex\build
       set "PATH=%PATH%;%DevEnvDir%CommonExtensions\Microsoft\CMake\CMake\bin"
       cmake -G "Visual Studio 15 2017 Win64" -DCMAKE_PREFIX_PATH=c:\libcurl ^
       -DCURL_LIBRARY=c:\libcurl -DCURL_INCLUDE_DIR=c:\libcurl ..
       
     This produce `c:\Dev\moneymanagerex\build\MMEX.sln` file ready to be loaded into Visual Studio GUI.
   
   2. Open above solution file with `File`->`Open`->`Project/Solution...` menu
   command (or `Ctrl+Shift+O`).
   
   3. Run `Build`->`Build Solution` menu command (or `Ctrl+Shift+B`). This will
   compile MMEX and propagate support files into right directories.
   
   4. Now you can run MMEX with `Debug`->`Start Without Debugging` menu command
   (`Ctrl+F5`) or start debugging session with `Debug`->`Start Debugging`
   (`F5`).

5. To create binary package (you need to have [NSIS] installed for this) build
   `PACKAGE` project.
   
[Download sources of curl]:
    //curl.haxx.se/latest.cgi?curl=zip
[libcurl]:
    https://curl.haxx.se/libcurl/
