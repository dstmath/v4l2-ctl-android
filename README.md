# v4l2-ctl-android
v4l2-ctl for android
# build for android
```
ndk_version=24.0.8215888
android_ndk=/{your ndk path}/${ndk_version}
# armeabi-v7a, arm64-v8a
abi=armeabi-v7a

mkdir build
cd build

cmake -G"Unix Makefiles" -DCMAKE_TOOLCHAIN_FILE=${android_ndk}/build/cmake/android.toolchain.cmake -DANDROID_NDK=${android_ndk} -DCMAKE_SYSTEM_NAME=Android -DANDROID_PLATFORM=android-21 -DCMAKE_BUILD_TYPE=Release -DANDROID_ABI=${abi} -DAndroid=ON -DANDROID_NATIVE_API_LEVEL=21 ..
make -j8
```