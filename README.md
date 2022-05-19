# Open-CMSIS-CDI API

Below is the initial list of proposed APIs that may be standardized as part of the **Open-CMSIS-CDI** project.

The proposed API interfaces are selected to enable:
  - Firmware update and security primitives on every device
  - Allowing IoT applications to runs on a broad range of physical devices as well as virtual hardware
  - Allow free choice of IoT software stacks or RTOS that work best for your application

>Notes:
> - It is proposed to re-use existing interfaces that have adoption. With the list below we provide access to existing material.
> - The list should be considered as Work-in-Progress and not as committed list of API interfaces.
> - The [Open-CMSIS-CDI](https://www.open-cmsis-cdi.org) working group should decide the final scope of interfaces and/or technical modifications.

Refer to [**www.open-cmsis-cdi.org**](https://www.open-cmsis-cdi.org) for details about the formation of Open-CMSIS-CDI working group.

## HAL APIs

### Required

|API|Candidate|Documentation|Headers|Tests|Pack|Ownership|
|---|---------|-------------|-------|-----|----|--------|
| CMSIS-Core | CMSIS-Core | [Documentation](https://arm-software.github.io/CMSIS_5/Core/html/index.html) | [Header](https://github.com/ARM-software/CMSIS_5/tree/develop/CMSIS/Core) | [Tests](https://github.com/ARM-software/CMSIS_5/tree/develop/CMSIS/CoreValidation) | [Pack](https://www.keil.com/dd2/pack/) | Arm |
| USART | CMSIS-Driver USART | [Documentation](https://arm-software.github.io/CMSIS_5/Driver/html/group__usart__interface__gr.html) | [Header](https://github.com/ARM-software/CMSIS_5/blob/develop/CMSIS/Driver/Include/Driver_USART.h) | [Tests](https://github.com/ARM-software/CMSIS-Driver_Validation) | [Pack](https://www.keil.com/dd2/pack/) | Open-CMSIS-CDI |
| Storage (Flash) | CMSIS-Driver Flash | [Documentation](https://arm-software.github.io/CMSIS_5/Driver/html/group__flash__interface__gr.html) | [Header](https://github.com/ARM-software/CMSIS_5/blob/develop/CMSIS/Driver/Include/Driver_Flash.h) | No tests | [Pack](https://www.keil.com/dd2/pack/) | Open-CMSIS-CDI |

### Optional

|API|Candidate|Documentation|Headers|Tests|Pack|Ownership|
|---|---------|-------------|-------|-----|----|--------|
| Watchdog | Mbed HAL Watchdog | [Documentation](https://gitlab.arm.com/iot/open-iot-sdk/mcu-driver-hal/mcu-driver-hal/-/blob/main/docs/porting/api/Watchdog.md) | [Header](https://gitlab.arm.com/iot/open-iot-sdk/mcu-driver-hal/mcu-driver-hal/-/blob/main/hal/include/hal/watchdog_api.h) | [Tests](https://gitlab.arm.com/iot/open-iot-sdk/mcu-driver-hal/mcu-driver-hal/-/tree/main/tests/mbed_hal) | No pack | Open-CMSIS-CDI |
| GPIO | Mbed HAL GPIO | [Documentation](https://gitlab.arm.com/iot/open-iot-sdk/mcu-driver-hal/mcu-driver-hal/-/blob/main/docs/porting/api/gpio.md) | [Header](https://gitlab.arm.com/iot/open-iot-sdk/mcu-driver-hal/mcu-driver-hal/-/blob/main/hal/include/hal/gpio_api.h) | [Tests](https://gitlab.arm.com/iot/open-iot-sdk/mcu-driver-hal/mcu-driver-hal/-/tree/main/tests/mbed_hal_fpga_ci_test_shield) | No pack | Open-CMSIS-CDI |
| Ticker | CMSIS-RTOS2 OS Tick | [Documentation](https://arm-software.github.io/CMSIS_5/RTOS2/html/rtos_os_tick_api.html) | [Header](https://github.com/ARM-software/CMSIS_5/blob/develop/CMSIS/RTOS2/Include/os_tick.h) | No tests | [Pack](https://www.keil.com/dd2/pack/) | Open-CMSIS-CDI |

## Middleware APIs
### Required

|API|Candidate|Documentation|Headers|Tests|Pack|Ownership|
|---|---------|-------------|-------|-----|----|--------|
| PSA Crypto | PSA Crypto | [Documentation](https://developer.arm.com/documentation/ihi0086/a/?lang=en) | [Header](https://github.com/ARM-software/psa-arch-tests/tree/main/api-specs/crypto) | [Tests](https://github.com/ARM-software/psa-arch-tests/tree/main/api-tests/dev_apis/crypto) | [Pack](https://www.keil.com/dd2/pack/) | PSA |
| PSA FWU | PSA FWU | [Documentation](https://developer.arm.com/documentation/ihi0093/0000/?lang=en) | [Header](https://github.com/ARM-software/psa-fwu-api) | No tests | [Pack](https://www.keil.com/dd2/pack/) | PSA |

### Optional
|API|Candidate|Documentation|Headers|Tests|Pack|Ownership|
|---|---------|-------------|-------|-----|----|--------|
| PSA Secure Storage | PSA Secure Storage | [Documentation](https://developer.arm.com/-/media/Files/pdf/PlatformSecurityArchitecture/Implement/IHI0087-PSA_Storage_API-1.0.0.pdf?revision=810a2412-bca0-46e1-a801-f48729a32e47) | [Header](https://github.com/ARM-software/psa-arch-tests/tree/main/api-specs/storage) | [Tests](https://github.com/ARM-software/psa-arch-tests/tree/main/api-tests/dev_apis/storage) | [Pack](https://www.keil.com/dd2/pack/) | PSA |
| PSA Attestation | PSA Attestation | [Documentation](https://developer.arm.com/-/media/Files/pdf/PlatformSecurityArchitecture/Implement/IHI0085-PSA_Attestation_API-1.0.2.pdf?revision=eef78753-c77e-4b24-bcf0-65596213b4c1) | [Header](https://github.com/ARM-software/psa-arch-tests/tree/main/api-specs/attestation) | [Tests](https://github.com/ARM-software/psa-arch-tests/tree/main/api-tests/dev_apis/initial_attestation) | [Pack](https://www.keil.com/dd2/pack/) | PSA |
| RTOS | CMSIS-RTOS2 | [Documentation](https://arm-software.github.io/CMSIS_5/RTOS2/html/index.html) | [Header](https://github.com/ARM-software/CMSIS_5/tree/develop/CMSIS/RTOS2) | [Tests](https://github.com/ARM-software/CMSIS-RTOS2_Validation) | [Pack](https://www.keil.com/dd2/pack/) | Open-CMSIS-CDI |
| Sockets | MDK IoT Sockets | [Documentation](https://mdk-packs.github.io/IoT_Socket/html/index.html) | [Header](https://github.com/MDK-Packs/IoT_Socket) | [Tests](https://github.com/ARM-software/CMSIS-Driver_Validation/blob/master/Source/DV_WIFI.c) | [Pack](https://www.keil.com/dd2/pack/) | Open-CMSIS-CDI |
