cmake_minimum_required(VERSION 3.10.0)
project(CppUtil)

add_compile_options(-std=c++14)

include_directories(
    include
)

find_package(libevent REQUIRED)

aux_source_directory(src/serial SERIAL_SRC)
aux_source_directory(src/network NETWORK_SRC)

add_library(CppUtil
    ${SERIAL_SRC}
    ${NETWORK_SRC}
)

target_link_libraries(CppUtil
    libevent
)