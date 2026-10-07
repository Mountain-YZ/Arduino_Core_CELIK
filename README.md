# Arduino_Core_CELIK
Arduino core for the **ÇELİK MCU**, a 32-bit RISC-V microcontroller by
[Yongatek Microelectronics](https://www.yongatek.com).

> Status: skeleton. No public datasheet, pinout or SDK yet; this core does not
> build sketches.

## ÇELİK MCU

| | |
|---|---|
| CPU | 32-bit single-core RISC-V |
| Clock | 24 – 50 MHz |
| Memory | 32 KiB ROM, 64 KiB RAM, 128 KiB Flash, 256 B OTP |
| Timers / PWM | 3× 16-bit timer, 6-channel PWM |
| Serial | 3× UART, 2× SPI, 2× I2C |
| GPIO | 56 pins, programmable IO mux |
| Analog | 10-channel 12-bit ADC |
| Touch | 8-channel touch-sense controller |
| Debug | JTAG |
| ID | 64-bit unique ID per chip |
| Package | 64-pin QFN |
| Supply | 4.5 – 5.5 V |
| Temperature | -20 – 85 °C (ambient) |

## Structure

```
platform.txt          toolchain and build recipes
boards.txt            board definitions
cores/celik/          Arduino core (Arduino.h, main.cpp)
variants/celik_dev/   board pin mapping (pins_arduino.h)
```

## License

[LGPL-2.1-or-later](LICENSE), same as the upstream Arduino cores.
