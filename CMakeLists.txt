
# xwf

SET(COMPILE_DEFINITIONS -Werror)

include_directories(${PROJECT_SOURCE_DIR})
include_directories(~/development/wifi/linux/include)
include_directories(~/development/wifi/raspberrypi-omxcam/include)

link_directories(~/development/wifi/pi3/usr/lib/arm-linux-gnueabihf)

add_executable(tx ${COMMON_SOURCES} tx.c lib.c fec.c)
add_executable(xtx ${COMMON_SOURCES} tx.c lib.c fec.c)

target_link_libraries(tx rt pcap)
target_link_libraries(xtx rt pcap)

install(TARGETS tx xtx RUNTIME DESTINATION bin)
