# vcpkg-with-visual-studio2017
This repository shows how to use c++ package manager vcpkg with visual studio 2017

1. First clone the letest vcpkg manager from github

```
> git clone https://github.com/Microsoft/vcpkg.git
> cd vcpkg
```
2. Open the powershell in vcpkg directory and run
```
PS> .\bootstrap-vcpkg.bat
 ```
 3. Now do intergate 
 ```
 PS> .\vcpkg integrate install
 ```
4. Now add the vcpkge.exe path to the env variabel so that u can use call vcpkg from anywhere

5. Now install package u want, like (ex: opencv)

```
vcpkg install opencv:x64-windows
```

6. Create a folder `vcpkg-opencv-src` will have the cpp file and CMakeLists.txt file

Create CMakeLists.txt in vcpkg-opencv-src/CMakeLists.txt and paste 
```
cmake_minimum_required( VERSION 3.0 )
set( CMAKE_TOOLCHAIN_FILE "G:/vcpkg/scripts/buildsystems/vcpkg.cmake" )

# Create Project
project( solution )
add_executable( project main.cpp )

# Set OpenCVConfig.cmake Search Directory
set( OpenCV_DIR )
if( NOT CMAKE_CL_64 )
  set( OpenCV_DIR "G:/vcpkg/installed/x86-windows/share/opencv" )
else()
  set( OpenCV_DIR "G:/vcpkg/installed/x64-windows/share/opencv" )
endif()

# Find Package
find_package( OpenCV REQUIRED )

if( OpenCV_FOUND )
  # Additional Include Directories
  include_directories( ${OpenCV_INCLUDE_DIRS} )

  # Additional Library Directories
  link_directories( ${OpenCV_LIB_DIR} )

  # Additional Dependencies
  target_link_libraries( project ${OpenCV_LIBS} )
endif()
```
7. Create a empty folder vcpkg-opencv-src-build

8. Now open cmake and set the source code folder and the build folder (ex:like in the pic)

![gerg](https://user-images.githubusercontent.com/11449967/60939884-3ae3a800-a2fb-11e9-8056-48582e8193b5.PNG)

9. Now do configure and now press generate button on cmake this will produce the visual studio project 

10. Now open the visual studio project and run the open cv c++ code .

Thanks
