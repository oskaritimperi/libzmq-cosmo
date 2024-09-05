`libzmq-cosmo.patch` contains patches to ZeroMQ 4.3.5 to make it possible to compile with cosmocc.

`cosmo-toolchain.cmake` contains a CMake toolchain description that you can use to compile ZeroMQ with.

For example:

```
curl -L -O https://github.com/zeromq/libzmq/releases/download/v4.3.5/zeromq-4.3.5.tar.gz
tar xf zeromq-4.3.5.tar.gz
cd zeromq-4.3.5
git apply ~/libzmq-cosmo.patch
cmake -DCMAKE_TOOLCHAIN_FILE=~/cosmo-toolchain.cmake -S . -B build-cosmo -DBUILD_SHARED=OFF
cmake --build build-cosmo --parallel
```
