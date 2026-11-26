# Hybridus VGM Display — verification notes

This repository documents an independent, unofficial RP2040 display firmware experiment for the Video Game Module for Flipper Zero. It is not affiliated with or endorsed by Flipper Devices Inc. or DarkFlippers, and it is not an Unleashed branch or release. “Flipper Zero” is a trademark of Flipper Devices Inc.; “Video Game Module” identifies the hardware.

## v0.3.1 preview

The [independent VGM Display 0.3.1 pre-release](https://github.com/ANTONiO-eagle/hybridus-vgm-display/releases/tag/vgm-display-v0.3.1-preview) contains the RP2040 UF2, matching reconstructed source archive and separate Desktop Settings 0.2 files. Use the four named assets and SHA-256 values in the release notes, not GitHub’s generated source links.

The device owner reported that screen mirroring, decorative side panels, and display inversion worked on a 1920×1080 monitor. This is the monitor resolution, not the signal resolution produced by the module.

Two local builds from reconstructed source matched the tested UF2 byte for byte. The file is 306,688 bytes and has 599 consecutive, aligned 256-byte RP2040 payloads; it has no non-flash blocks. This satisfies the [Video Game Module Tool's documented file-format constraints](https://lab.flipper.net/apps/video_game_module_tool). This check did not test flashing with the tool.

UF2 SHA-256: `097dc0bd407f39b558e9baa4ad86c371bdfbfed276a223c862aa1545ecc8d71c`.

## Desktop Settings companion

The device owner confirmed that the separate settings app worked on Hybridus UI for Flipper Zero F7 (API 88.27). The app relies on Hybridus-specific host functions. This does not establish complete end-to-end compatibility with the VGM preview, including RGB synchronization and settings persistence after a power cycle. The available companion source snapshot omits five Hybridus host implementations; it is not sufficient on its own to reproduce the complete host and app stack.

## Source, attribution and licensing

The `main` branch holds documentation; downloadable artifacts are attached to the linked pre-release.

Flipper Devices added an [upstream MIT license](https://github.com/flipperdevices/video-game-module/blob/554cd11aae18785bfcee8577feafb59d2e44897b/LICENSE) to VGM `dev` at `554cd11`; see [Pavel Zhovner’s confirmation in #19](https://github.com/flipperdevices/video-game-module/issues/19#issuecomment-7175061093). Issue #19 was closed as completed. The preview uses [VGM 0.1.0 (`f18ad44`)](https://github.com/flipperdevices/video-game-module/tree/f18ad4481ef04449aaae55a4d5556923effef276), which predates that addition and has no root `LICENSE`. The reply does not explicitly identify that older revision or the separate [pinned `flipperzero-protobuf` revision `1956b83`](https://github.com/flipperdevices/flipperzero-protobuf/tree/1956b83bba99313ee8d8386e5d35d0549341ca26); the terms for the exact base, packaged schemas and related generated code remain to be confirmed. The new upstream license is not a blanket clearance for the current artifacts or the separate FAP. See the [current component inventory](THIRD_PARTY_NOTICES.md).
