# OpenCvSlim

- This project provides the slim build of OpenCv library for the **Android**, **Windows** and **ARM Linux** platforms.

- Currently there're binary packages for OpenCv **2.4.13.7**.


# Tips

* The OpenCvSlim  only build basic OpenCv operators and  common image processing functions.

* ```cv::imread``` and ```cv::imwrite``` are reimplemented using [stb](https://github.com/nothings/stb) for smaller size. 

# Modules included

|module|note|
|---|---|
|opencv_core|Mat, matrix operations|
|opencv_imgproc|resize, cvtColor, warpAffine|
|opencv_highgui|imread, imwrite|
|opencv_features2d|keypoint feature and matcher|
|opencv_photo|inpaint|
|opencv_video|opticalflow|


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





