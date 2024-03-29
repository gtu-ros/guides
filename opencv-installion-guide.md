# OpenCV Installion to Jetson

```shell
git clone https://github.com/opencv/opencv
```

```shell
cd opencv
```

```shell
git checkout <VERSION>
```

Return home folder

```shell
cd
```

```shell
git clone https://github.com/opencv/opencv_contrib
```

```shell
cd opencv_contrib
```

```shell
git checkout <VERSION>
```


Return home folder

```shell
cd
```

```shell

mkdir opencv_build
```

```shell
cd opencv_build
```

```shell
cmake -DCMAKE_BUILD_TYPE=Release \
-DOPENCV_EXTRA_MODULES_PATH=../opencv_contrib/modules \
-DBUILD_TESTS=OFF \
-DBUILD_DOCS=OFF \
-DBUILD_EXAMPLES=OFF \
-DBUILD_JASPER=ON \
-DBUILD_JAVA=OFF \
-DBUILD_JPEG=ON \
-DBUILD_OPENEXR=ON \
-DBUILD_OPENJPEG=ON \
-DBUILD_PERF_TESTS=OFF \
-DBUILD_PNG=ON \
-DBUILD_WEBP=ON \
-DBUILD_TIFF=ON \
-DBUILD_ZLIB=ON \
-DWITH_TBB=ON \
-DBUILD_TBB=ON \
-DWITH_CUDA=ON \
-DBUILD_opencv_cudacodec=OFF \
-DWITH_NVCUVID=ON \
-DOPENCV_DNN_CUDA=ON \
-DWITH_OPENGL=ON \
-DOpenGL_GL_PREFERENCE=GLVND \
-DWITH_QT=ON \
-DWITH_GTK=OFF \
-DWITH_VTK=OFF \
-DWITH_LIBV4L=ON \
-DCUDA_FAST_MATH=ON \
-DENABLE_FAST_MATH=ON \
-DCUDA_ARCH_BIN="7.5" \
-DOPENCV_ENABLE_NONFREE=ON \
-DBUILD_LIST=core,highgui,improc,videoio,aruco,cudaarithm,cudabgsegm,cudafeatures2d,cudafilters,cudaimgproc,cudalegacy,cudaobjdetect,cudaoptflow,cudastereo,cudawarping,cudev ../opencv
```
