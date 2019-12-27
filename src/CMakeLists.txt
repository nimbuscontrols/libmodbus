set(SOURCE_FILES modbus.c
        modbus-data.c
        modbus-gpio.c
        modbus-rtu.c
        modbus-tcp.c)

add_library(modbus SHARED ${SOURCE_FILES})
add_library(modbusS STATIC ${SOURCE_FILES})

set_target_properties(
        modbus
        PROPERTIES
        VERSION ${LIBMODBUS_VERSION_MAJOR}.${LIBMODBUS_VERSION_MINOR}.${LIBMODBUS_VERSION_MICRO}
        SOVERSION ${LIBMODBUS_VERSION_MAJOR})

install(TARGETS modbus modbusS
        LIBRARY
        DESTINATION lib
        ARCHIVE
        DESTINATION lib)

install(DIRECTORY ${CMAKE_SOURCE_DIR}/src/
        DESTINATION include/modbus
        FILES_MATCHING PATTERN "*.h*")

install(DIRECTORY ${CMAKE_BINARY_DIR}/include/
        DESTINATION include/modbus
        FILES_MATCHING PATTERN "*.h*")