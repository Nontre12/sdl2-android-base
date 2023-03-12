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
    PUBLIC lib/SDL_image
    PUBLIC lib/SDL_mixer/include)

option(SDL2IMAGE_INSTALL OFF)

target_link_libraries(main SDL2 SDL2_image SDL2_mixer)

add_subdirectory (lib/SDL)
add_subdirectory (lib/SDL_image)

add_subdirectory (lib/openssl)

add_subdirectory (lib/SDL_mixer/external/opus)
add_subdirectory (lib/SDL_mixer/external/opusfile)
add_subdirectory (lib/SDL_mixer/external/flac)
add_subdirectory (lib/SDL_mixer/external/libmodplug)
add_subdirectory (lib/SDL_mixer)
 