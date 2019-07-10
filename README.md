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

6. Create two folder one will have the cpp file and CMakeLists.txt file 

7. Now open cmake and set the source code folder and the build folder (ex:like in the pic)

![gerg](https://user-images.githubusercontent.com/11449967/60939884-3ae3a800-a2fb-11e9-8056-48582e8193b5.PNG)

8. Now do configure and now press generate button on cmake this will produce the visual studio project 

9. Now open the visual studio project and run the open cv c++ code .

Thanks
