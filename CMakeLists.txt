cmake_minimum_required(VERSION 3.16)
project(terrain_editor_raylib)

set(CMAKE_CXX_STANDARD 11)

include_directories(raylib/include)
link_directories(raylib/lib)
add_executable(terrain_editor_raylib editor/main.cpp)
IF (WIN32)
    target_link_libraries(terrain_editor_raylib raylib_win32 mingw32 m winmm)
ELSEIF (APPLE)
    target_link_libraries(terrain_editor_raylib raylib_mac "-framework Cocoa" "-framework IOKit" "-framework OpenGL")
ENDIF()
