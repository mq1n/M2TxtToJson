cmake_minimum_required(VERSION 3.8)
project(M2TxtToJson C CXX)
set(exe ${PROJECT_NAME})

SET(CMAKE_COLOR_MAKEFILE ON)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ../Bin)

add_definitions(-D_CRT_SECURE_NO_WARNINGS)
include_directories(${PROJECT_SOURCE_DIR}/3rd/modular-boost)

set(HEADERFILES
    ${PROJECT_SOURCE_DIR}/M2Stuffs/d3dtype.h
    ${PROJECT_SOURCE_DIR}/M2Stuffs/pool.h
    ${PROJECT_SOURCE_DIR}/M2Stuffs/stl.h
    ${PROJECT_SOURCE_DIR}/M2Stuffs/utils.h
    ${PROJECT_SOURCE_DIR}/M2Stuffs/FileLoader.h
    ${PROJECT_SOURCE_DIR}/M2Stuffs/TextFileLoader.h
    ${PROJECT_SOURCE_DIR}/Sources/Parser.h
)

set(SOURCEFILES
    ${PROJECT_SOURCE_DIR}/Sources/main.cpp
    ${PROJECT_SOURCE_DIR}/Sources/TxtParser.cpp
    ${PROJECT_SOURCE_DIR}/Sources/JsonParser.cpp
    ${PROJECT_SOURCE_DIR}/M2Stuffs/FileLoader.cpp
    ${PROJECT_SOURCE_DIR}/M2Stuffs/TextFileLoader.cpp
)

add_executable(${PROJECT_NAME} WIN32 ${HEADERFILES} ${SOURCEFILES})

