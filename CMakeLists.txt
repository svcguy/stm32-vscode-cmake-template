cmake_minimum_required(VERSION 3.13)

set(STM32_TOOLCHAIN_PATH "C:\\GCC\\9-2020-q2-update\\bin")
set(CMAKE_TOOLCHAIN_FILE ${CMAKE_CURRENT_SOURCE_DIR}/../stm32-cmake/cmake/stm32_gcc.cmake)

project(stm32-vscode-cmake-template C ASM)

stm32_fetch_cube(G0)

find_package(CMSIS COMPONENTS STM32G031J6 REQUIRED)

set(PROJECT_INCLUDES
    inc/main.h
)

set(PROJECT_SOURCES
    src/main.c
)

target_include_directories(stm32-vscode-cmake-template ${PROJECT_INCLUDES})
add_executable(stm32-fetch-g0 ${PROJECT_SOURCES})
target_link_libraries(stm32-fetch-g0 HAL::STM32::G031J6 STM32::NoSys)