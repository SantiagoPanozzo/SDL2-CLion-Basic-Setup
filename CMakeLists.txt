cmake_minimum_required(VERSION 3.23)

project(testSDL2)

set(CMAKE_CXX_STANDARD 14)

set(CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake/modules)

find_package(SDL2 REQUIRED)
find_package(SDL2_image REQUIRED)
find_package(SDL2_ttf REQUIRED)

include_directories(
        ${SDL2_INCLUDE_DIR}
        ${SDL2_IMAGE_INCLUDE_DIR}
        ${SDL2_TTF_INCLUDE_DIR})

add_executable(testSDL2 main.cpp)

target_link_libraries(testSDL2 ${SDL2_LIBRARY} -lmingw32 -lSDL2main -lSDL2 -mwindows)
target_link_libraries(testSDL2 ${SDL2_IMAGE_LIBRARY} -lmingw32 -lSDL2main -lSDL2 -mwindows)
target_link_libraries(testSDL2 ${SDL2_TTF_LIBRARY} -lmingw32 -lSDL2main -lSDL2 -mwindows)