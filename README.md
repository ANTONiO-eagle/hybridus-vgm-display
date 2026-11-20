# Hybridus VGM Display — verification notes

This repository documents an independent, unofficial RP2040 display firmware experiment for the Video Game Module for Flipper Zero. It is not affiliated with or endorsed by Flipper Devices Inc. or DarkFlippers, and it is not an Unleashed branch or release. “Flipper Zero” is a trademark of Flipper Devices Inc.; “Video Game Module” identifies the hardware.

## v0.3.1 preview

The device owner reported that screen mirroring, decorative side panels, and display inversion worked on a 1920×1080 monitor. This is the monitor resolution, not the signal resolution produced by the module.

Two local builds from reconstructed source matched the tested UF2 byte for byte. The file is 306,688 bytes and has 599 consecutive, aligned 256-byte RP2040 payloads; it has no non-flash blocks. This satisfies the [Video Game Module Tool's documented file-format constraints](https://lab.flipper.net/apps/video_game_module_tool). This check did not test flashing with the tool.

UF2 SHA-256: `097dc0bd407f39b558e9baa4ad86c371bdfbfed276a223c862aa1545ecc8d71c`.

## Desktop Settings companion

The device owner confirmed that the separate settings app worked on Hybridus UI for Flipper Zero F7 (API 88.27). The app relies on Hybridus-specific host functions. This does not establish complete end-to-end compatibility with the VGM preview, including RGB synchronization and settings persistence after a power cycle. No public companion download is provided here.

## Source and release status

This is a documentation-only repository. It does not distribute firmware, an app binary, source code, upstream assets, or patches. No project-wide license is asserted for the firmware. The original VGM firmware is maintained by [Flipper Devices](https://github.com/flipperdevices/video-game-module); the preview is based on upstream [v0.1.0](https://github.com/flipperdevices/video-game-module/releases/tag/0.1.0). Firmware distribution is pending confirmation of applicable terms. A separate companion app release depends on identifying its matching source and build configuration.
