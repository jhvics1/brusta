cmake_minimum_required(VERSION 3.0 FATAL_ERROR)
project(brustar)

include_directories(/usr/lib/jvm/java-1.8.0-openjdk-amd64/include)
include_directories(/usr/lib/jvm/java-1.8.0-openjdk-amd64/include/linux)

find_package(Torch REQUIRED)

add_library(Model SHARED Model.cpp)
target_link_libraries(Model "${TORCH_LIBRARIES}")
set_property(TARGET Model PROPERTY CXX_STANDARD 11)
