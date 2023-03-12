cmake_minimum_required (VERSION 3.22.1)
project (Euphoria VERSION 1.0)

set (CMAKE_CXX_STANDARD 14)

add_library (
    main
    SHARED src/main.cpp)

target_include_directories (
    main 
    PUBLIC include
    PUBLIC lib/SDL/include
    PUBLIC lib/SDL_image)

option(SDL2IMAGE_INSTALL OFF)

target_link_libraries(main SDL2 SDL2_image)

add_subdirectory (lib/SDL)
add_subdirectory (lib/SDL_image)
