cmake_minimum_required(VERSION 3.4.1)

project (native C CXX)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -fexceptions")
add_library(native SHARED Cube.cpp native.cpp ndk_helper/shader.cpp
        ndk_helper/vecmath.cpp ndk_helper/tapCamera.cpp ndk_helper/interpolator.cpp
        ndk_helper/perfMonitor.cpp ndk_helper/GLContext.cpp ndk_helper/gl3stub.c)

include_directories(${CMAKE_CURRENT_SOURCE_DIR})
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/ndk_helper)

target_link_libraries(native log GLESv2 EGL)
