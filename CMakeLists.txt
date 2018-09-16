cmake_minimum_required(VERSION 3.0)
project(cat VERSION 2.2.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 14)

add_library(cat INTERFACE)
add_library(cat::cat ALIAS cat)

find_package(Threads)

target_include_directories(cat
  INTERFACE
    $<BUILD_INTERFACE:${CMAKE_CURRENT_LIST_DIR}>
    $<INSTALL_INTERFACE:include>)

# Create an install target
install(TARGETS cat
        EXPORT cat-config
        INCLUDES DESTINATION include)

install(EXPORT cat-config
        FILE cat-config.cmake
        NAMESPACE cat::
        DESTINATION share/cat/cmake)

install(DIRECTORY cat
        DESTINATION include FILES_MATCHING PATTERN "*.hpp")


install(FILES README.md DESTINATION . RENAME cat-Readme.md)

add_subdirectory(test)
add_subdirectory(example/parser)
