# STM32 template repository
### A template for developing for STM32 with CMSIS, CubeMX HAL, CubeMX LL using CMake and VSCode
Cloning this repo will give you a template that can be used to start STM32 projects simply.
### Prequisites
- [VSCode](https://code.visualstudio.com/)
- VSCode extension [CMake Tools](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cmake-tools)
- VSCode extension [Cortex-Debug](https://marketplace.visualstudio.com/items?itemName=marus25.cortex-debug)
- VSCode extension [C/C++](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools) 
- [GNU Arm Embedded Toolchain](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads)
- A debug probe supported by Cortex-Debug ([see here for list](https://github.com/Marus/cortex-debug))
### How to use
1. Clone this repository
    - `git clone https://github.com/svcguy/stm32-vscode-cmake-template <YOUR PROJECT NAME>`
    - `git submodule init`
    - `git submodule update`
2. Adjust paths and project specific settings
    - CMakeLists.txt
        - Change STM32_TOOLCHAIN_PATH to your ARM cross compile toolchain location
        - Change your project name to your desired project name
        - Change your STM32 family, device and components
    - launch.json
        - Set your paths to ST-LINK GDB server and STM32 Cube Programmer
        - Set your device
        - Set your svd file
3. Write your code in main.c and main.h.  Other files can be add as necessary.

For more information on stm32-cmake see the [repository](https://github.com/ObKo/stm32-cmake)
For more information on cortex-debug see the [repository](https://github.com/Marus/cortex-debug)
