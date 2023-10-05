add_executable(simon
        simon.c
        )

# pull in common dependencies
target_link_libraries(simon pico_stdlib)

# enable usb output, disable uart output
pico_enable_stdio_usb(simon 1)
pico_enable_stdio_uart(simon 0)

# create map/bin/hex file etc.
pico_add_extra_outputs(simon)

#add_subdirectory(hello_world)
