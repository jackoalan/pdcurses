cmake_minimum_required(VERSION 2.8)
project(pdcurses)

include_directories(.)

add_subdirectory(pdcurses)
add_subdirectory(win32)

add_library(pdcurses
            ${MAIN_SOURCES})

# Export for external inclusion
export(TARGETS pdcurses FILE pdcurses-targets.cmake)
set(PDCURSES_TARGETS_FILE ${CMAKE_BINARY_DIR}/pdcurses-targets.cmake)
configure_file(pdcurses-config.cmake.in pdcurses-config.cmake)
export(PACKAGE pdcurses)

