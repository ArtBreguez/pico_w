cmake_minimum_required(VERSION 3.13)

include($ENV{PICO_SDK_PATH}/pico_sdk_init.cmake)

set(PICO_BOARD pico_w)

project(test_project)

pico_sdk_init()

add_executable(test test.c)

pico_enable_stdio_usb(test 1)
pico_enable_stdio_uart(test 0)

pico_add_extra_outputs(test)

target_link_libraries(test pico_stdlib pico_cyw43_arch_none)