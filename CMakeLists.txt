cmake_minimum_required(VERSION 3.5)

set(LIBMODBUS_VERSION_MAJOR 1)
set(LIBMODBUS_VERSION_MINOR 3)
set(LIBMODBUS_VERSION_MICRO 6)
project (libmodbus)

configure_file(${CMAKE_SOURCE_DIR}/src/modbus-version.h.in
        ${CMAKE_BINARY_DIR}/include/modbus-version.h)

option(HAVE_DECL_TIOCM_RTS "TIOM RTS flag" OFF)

configure_file(${CMAKE_SOURCE_DIR}/config-cmake.h.in
        ${CMAKE_BINARY_DIR}/include/config.h)

include_directories(${CMAKE_BINARY_DIR}/include)
add_subdirectory(src)