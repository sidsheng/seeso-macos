cmake_minimum_required(VERSION 3.5)
project(opencv)

add_library(opencv INTERFACE)

find_package(OpenCV REQUIRED)
set(OPENCV_INCLUDE_PATH "${OpenCV_INCLUDE_DIRS}")
set(OPENCV_LIB "${OpenCV_LIBS}")

target_link_libraries(opencv INTERFACE ${OPENCV_LIB})
target_include_directories(opencv INTERFACE ${OPENCV_INCLUDE_PATH})

set(OPENCV_LIB ${OPENCV_LIB} PARENT_SCOPE)
set(OPENCV_DLL ${OPENCV_DLL} PARENT_SCOPE)
message("OpenCV include path: ${OPENCV_INCLUDE_PATH}")
message("OpenCV lib: ${OPENCV_LIB}")
