cmake_minimum_required(VERSION 3.10)

project(projectsg)

find_package(SDL2 REQUIRED)
find_package(SDL2_gfx REQUIRED)
find_package(SDL2_ttf REQUIRED)

add_executable(${PROJECT_NAME}
    ${CMAKE_CURRENT_SOURCE_DIR}/projectsg/main.cpp
)

target_link_libraries(${PROJECT_NAME}
    mingw32
    ${SDL2MAIN_LIBRARY}
    ${SDL2_GFX_LIBRARY}
    ${SDL2_TTF_LIBRARY}
    ${SDL2_LIBRARY}
    projectsg-gui
    projectsg-physics
    -static
)

target_include_directories( ${PROJECT_NAME}
    PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}
    PUBLIC ${SDL2_INCLUDE_DIR}
)
