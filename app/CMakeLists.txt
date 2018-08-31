# For more information about using CMake with Android Studio, read the
# documentation: https://d.android.com/studio/projects/add-native-code.html

# Sets the minimum version of CMake required to build the native library.

cmake_minimum_required(VERSION 3.4.1)

set (PATH_TO_JNI_LAYER src/main/cpp)

file(GLOB FILES_JNI_LAYER "${PATH_TO_JNI_LAYER}/*.cpp")

add_library(native-lib SHARED
        src/main/cpp/NativeMedia.cpp
        )

target_link_libraries(native-lib
 log android EGL GLESv2 GLESv3)