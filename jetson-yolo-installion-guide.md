# Yolo Installion to Jetson

Yolo Jetson Xaiver NX installion (production) guide

```shell
git clone https://github.com/AlexeyAB/darknet.git
cd darknet
mkdir build_release
```

```shell
cmake -DBUILD_AS_CPP=ON \
-DBUILD_SHARED_LIBS=OFF \
-DENABLE_VCPKG_INTEGRATION=OFF \
-DVCPKG_BUILD_OPENCV_WITH_CUDA=OFF \
-DVCPKG_USE_OPENCV4=OFF \
-DCMAKE_CUDA_ARCHITECTURES=72 \
-DCMAKE_INSTALL_PREFIX=/usr/local \
-DINSTALL_BIN_DIR=/usr/local/bin \
-DINSTALL_LIB_DIR=/usr/local/lib \
-DCMAKE_BUILD_TYPE=Release ..
```

```shell
make -j6
````


```shell
sudo make install
```
