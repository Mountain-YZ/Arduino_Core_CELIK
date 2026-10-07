# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

An Arduino platform (core) for the Yongatek **ÇELİK MCU**, a 32-bit RISC-V chip. It is a **skeleton**: no public datasheet, pinout or SDK exists yet, so it does not compile sketches. Chip specs are in [README.md](../README.md). Do not invent register maps, pin assignments, ISA extensions or toolchain flags. Mark unknowns as placeholders.

## Layout (Arduino Platform Specification)

The repo root is the architecture folder. Arduino discovers it at `<sketchbook>/hardware/<vendor>/<arch>/`.

- `platform.txt`: platform name/version. Toolchain paths and `recipe.*` build patterns go here. None exist yet, which is why nothing builds.
- `boards.txt`: board menu entries (`celik_dev.*`). `build.core` selects `cores/<name>/` and `build.variant` selects `variants/<name>/`. `build.mcu` and `build.f_cpu` are placeholders.
- `cores/celik/`: core sources (`Arduino.h`, `main.cpp`), currently stubs.
- `variants/celik_dev/pins_arduino.h`: per-board pin counts and mapping.

New boards: add a `<board>.*` block in `boards.txt` and, if the pinout differs, a new `variants/<board>/`.

## Build / test

No build, lint or test tooling exists. Once `platform.txt` has toolchain recipes, the core can be checked by compiling a sketch with `arduino-cli compile --fqbn <vendor>:<arch>:celik_dev`. The vendor and arch come from the install folder names.

## Conventions

- Line endings are LF (`.gitattributes`).
- License: LGPL-2.1-or-later, matching upstream Arduino cores.
