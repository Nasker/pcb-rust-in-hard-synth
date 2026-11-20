# RustInSynthPCB

Mainboard PCB for the **RinSynth** ESP32-S3 synthesizer — a standalone studio/performance
synth module with real analog I/O, DIN MIDI and an open firmware.

Companion firmware: [`rinsynth-esp32`](../rinsynth-esp32) (Rust, ESP-IDF).

## Overview

Single-PCB design. All user-facing components live on the front face; the ESP32-S3
development board is soldered as a receptor/socket on the **back** face.

| Block | Parts |
| :--- | :--- |
| MCU | ESP32-S3-DevKitC-1-**N16R8** (16 MB flash / 8 MB octal PSRAM), back-face mount |
| Audio in | TI PCM1860 stereo ADC (TSSOP-30) |
| Audio out | TI PCM5102A stereo DAC (TSSOP-20) |
| Jacks | 4× 6.35 mm right-angle jacks (Neutrik-clone footprint, 6 pins, no locating pegs) |
| MIDI | DIN-5 MIDI **input** (H11L1 optocoupler) — consumer only, no MIDI out |
| Controls | 4× ACP CA9 SMD potentiometers, 4× Panasonic EVQPU tactile switches, Bourns PEC11S encoder w/ push |
| Display | 1.3" 128×64 SPI OLED |
| Storage | microSD (Würth 693072010801) |
| Power | LP5907-3.3 LDO + ferrite filtering for the analog rail |

I2S clocks use single-resistor source termination at the MCU (option-B topology);
GPIO33–37 are avoided because they serve the octal PSRAM bus.

## Repo layout

```
RustInSynthPCB.kicad_pro / .kicad_sch / .kicad_pcb   # project, root sheet, board
ui.kicad_sch / audio.kicad_sch / midi.kicad_sch / mcu.kicad_sch   # subsheets
Local_Libraries/     # project symbols, footprints and 3D models
Enclosure/           # enclosure CAD + STEP export
JLC_BOM.csv          # JLCPCB/LCSC-sourced BOM (C-numbers, assembly notes)
Images/, Schematics/ # renders & reference PDFs
```

## Status

Rev 1 — routed, DRC clean (0 unconnected / 0 shorts). Work-in-progress; see the
`develop` branch for current changes.

## License

MIT — see [LICENSE.txt](LICENSE.txt)
