cmake_minimum_required(VERSION 3.12)
project(Minesweeper)

set(CMAKE_MODULE_PATH "${PROJECT_SOURCE_DIR}/cmake")
set(CMAKE_CXX_STANDARD 14)

find_package(SDL2 REQUIRED)
find_package(SDL2_ttf REQUIRED)
find_package(SDL2_image REQUIRED)
find_package(SDL2_mixer REQUIRED)


include_directories(
        "source/"
        ${SDL2_INCLUDE_DIR}
        ${SDL2_TTF_INCLUDE_DIR}
        ${SDL2_IMAGE_INCLUDE_DIR}
        ${SDL2_MIXER_INCLUDE_DIR}
)
set(SOURCE_FILES
        source/src/main.cpp
        source/headers/Rect.h
        source/src/Rect.cpp
        source/headers/Game.h
        source/src/Game.cpp
        source/headers/Replay.h
        source/src/Replay.cpp
        source/headers/Board.h
        source/src/Board.cpp
        source/headers/LaunchGame.h
        source/src/LaunchGame.cpp
        source/headers/Texture.h
        source/src/Texture.cpp
        source/headers/Sound.h
        source/src/Sound.cpp)

add_executable(Minesweeper ${SOURCE_FILES})

target_link_libraries(Minesweeper
        ${SDL2_LIBRARY}
        ${SDL2_TTF_LIBRARY}
        ${SDL2_IMAGE_LIBRARY}
        ${SDL2_MIXER_LIBRARY}
        )

