# OpenCvSlim

- This project provides the slim build of OpenCv library for the **Android**, **Windows** and **ARM Linux** platforms.

- Currently there're binary packages for OpenCv **2.4.13.7** and **3.4.20**.

# OpenCvSlim Size
|package|size|
|---|---|
|OpenCvSlim-2.4.13.7-android.zip (arm64,armeabi,x64,x86)| 8.2MB |
|OpenCvSlim-2.4.13.7-armlinux.zip (aarch64,arm-linux-gnueabi,arm-linux-gnueabihf)| 7.9MB |
|OpenCvSlim-2.4.13.7-ubuntu-2004.zip | 2.8MB |
|OpenCvSlim-2.4.13.7-ubuntu-2204.zip | 2.8MB |
|OpenCvSlim-2.4.13.7-webassembly.zip (basic,simd,simd-threads)| 6.2MB |
|OpenCvSlim-2.4.13.7-win-vs2015.zip (x64,x86)| 6.7MB |
|OpenCvSlim-2.4.13.7-win-vs2017.zip (x64,x86)| 6.9MB |
|OpenCvSlim-2.4.13.7-win-vs2019.zip (x64,x86)| 7.5MB |
|OpenCvSlim-2.4.13.7-win-vs2022.zip (x64,x86)| 7.5MB |
|OpenCvSlim-3.4.20-android.zip (arm64,armeabi,x64,x86)| 16.4MB |
|OpenCvSlim-3.4.20-armlinux.zip (aarch64,arm-linux-gnueabi,arm-linux-gnueabihf)| 14.4MB |
|OpenCvSlim-3.4.20-ubuntu-2004.zip | 6.5MB |
|OpenCvSlim-3.4.20-ubuntu-2004.zip | 6.6MB |
|OpenCvSlim-3.4.20-webassembly.zip (basic,simd,simd-threads)| 11.2MB |
|OpenCvSlim-3.4.20-win-vs2015.zip (x64,x86)| 14.8MB |
|OpenCvSlim-3.4.20-win-vs2017.zip (x64,x86)| 15.4MB |
|OpenCvSlim-3.4.20-win-vs2017.zip (x64,x86)| 15.9MB |
|OpenCvSlim-3.4.20-win-vs2022.zip (x64,x86)| 15.9MB |


# Tips

* The OpenCvSlim  only build basic OpenCv operators and  common image processing functions.

* ```cv::imread``` and ```cv::imwrite``` are reimplemented using [stb](https://github.com/nothings/stb) for smaller size. 

# Modules included

|module|note|
|---|---|
|opencv_core|Mat, matrix operations ...|
|opencv_imgproc|resize, cvtColor, warpAffine, HoughLines, erode ...|
|opencv_highgui|imread, imwrite, imdecode, imencode ...|
|opencv_features2d|keypoint feature and matcher ...|
|opencv_photo|inpaint , fastNlMeansDenoising ...|
|opencv_video|opticalflow, KalmanFilter  ...|

- you can get more details in head file within directory of **opencv2** .


# Usage Android

1. Extract Zip  to ```<project dir>/app/src/main/jni/```
2. Modify ```<project dir>/app/src/main/jni/CMakeListst.txt``` to  link OpenCv

```cmake
set(OpenCV_DIR ${CMAKE_SOURCE_DIR}/OpenCvSlim-x.x.x-android/sdk/native/jni)
find_package(OpenCV REQUIRED)

target_link_libraries(target ${OpenCV_LIBS})
```


# Usage ARM Linux, Windows, Linux

1. Extract Zip to ```<project dir>/```
2. Modify ```<project dir>/CMakeListst.txt``` to link OpenCv
3. Set ```-DOpenCV_STATIC=ON``` to cmake option for windows build

```cmake
set(OpenCV_DIR ${CMAKE_SOURCE_DIR}/OpenCvSlim-x.x.x-armlinux/aarch64-linux-gnu/lib/cmake/opencv2)
find_package(OpenCV REQUIRED)

target_link_libraries(target ${OpenCV_LIBS})
```





