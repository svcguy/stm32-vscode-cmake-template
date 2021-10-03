cmake_minimum_required(VERSION 3.16)

# This line needs to be changed to your toolchain bin folder
set(STM32_TOOLCHAIN_PATH "C:\\GCC\\9-2020-q2-update\\bin")

set(CMAKE_TOOLCHAIN_FILE ${CMAKE_CURRENT_SOURCE_DIR}/stm32-cmake/cmake/stm32_gcc.cmake)

# You can change the project name here
# This determines the elf file name
set(PROJECT_NAME template)
project(${PROJECT_NAME} C ASM)

# Change the family here to match yours
stm32_fetch_cmsis(G0)
stm32_fetch_hal(G0)

# Change the family and mcu to match yours
find_package(CMSIS COMPONENTS STM32G031J6 REQUIRED)
find_package(HAL COMPONENTS STM32G0 REQUIRED)

set(PROJECT_INCLUDES
    ${CMAKE_CURRENT_SOURCE_DIR}/inc
)

set(PROJECT_SOURCES
    src/main.c
)

add_executable(${PROJECT_NAME} ${PROJECT_SOURCES})

target_include_directories(${PROJECT_NAME} PUBLIC ${PROJECT_INCLUDES})

# Change to mcu and required components to match your requirements
target_link_libraries(${PROJECT_NAME}
     CMSIS::STM32::G031J6
     HAL::STM32::G0::LL_UTILS
     HAL::STM32::G0::LL_RCC
     STM32::Nano
)

stm32_print_size_of_target(${PROJECT_NAME})