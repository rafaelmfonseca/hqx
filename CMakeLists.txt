project(hqx)

cmake_minimum_required(VERSION 2.8)

include_directories(
	"include")

file(GLOB HQX_SOURCES
	"source/HQx.cc"
	"source/HQ2x.cc"
	"source/HQ3x.cc")

add_library(hqx ${HQX_SOURCES})
set_target_properties(hqx PROPERTIES
    OUTPUT_NAME "hqx"
    ARCHIVE_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}"
    LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}"
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}"
    PREFIX "lib" )

add_executable(hqxlib "source/main.cc")
target_link_libraries(hqxlib hqx)
set_target_properties(hqxlib PROPERTIES
    OUTPUT_NAME "hqxlib"
    ARCHIVE_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}"
    LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}"
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}" )
