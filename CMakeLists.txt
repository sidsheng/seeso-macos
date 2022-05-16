cmake_minimum_required(VERSION 3.5)
project(seeso_macos)


set(CMAKE_CXX_STANDARD 14)


add_subdirectory(opencv)
add_subdirectory(seeso)

add_executable(seeso_macos main.cpp
        tracker_manager.cc
        camera_thread.cc
        view.cc
        priority_mutex.cc)

target_link_libraries(seeso_macos PUBLIC opencv seeso)

if (DEFINED SEESO_TEST_KEY)
    ADD_DEFINITIONS(-DSEESO_TEST_KEY=${SEESO_TEST_KEY})
endif()