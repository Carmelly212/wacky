cmake_minimum_required(VERSION 3.12)
project(wacky v1)

add_library(
    libwacky
    wacky_math.c
    wacky_math.h 
)
add_executable(EXEwacky wacky.c)

target_link_libraries(EXEwacky PRIVATE libwacky)