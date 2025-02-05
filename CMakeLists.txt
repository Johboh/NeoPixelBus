# FastLED
# https://github.com/FastLED/FastLED
# MIT License

cmake_minimum_required(VERSION 3.5)

# Collect all source files recursively
file(GLOB_RECURSE LIB_SRCS
    "src/*.*"
)

set(required_components arduino-esp32 esp_driver_rmt driver)

idf_component_register(COMPONENT_NAME "neopixelbus"
                        SRCS ${LIB_SRCS}
                        INCLUDE_DIRS "./src/"
                        REQUIRES ${required_components})
