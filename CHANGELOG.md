# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0-alpha.19] - 2021-12-24

### Fixed
- Fixed incorrect metadata checksum for the firmware installer for SPIKE hubs.

## [1.0.0-alpha.18] - 2021-12-03

### Added
- Added support for Python 3.10.

### Fixed
- Fixed `tqdm` dependency version.
- Fixed being unable to set the name of SPIKE hubs.

## [1.0.0-alpha.17] - 2021-10-25

### Added
- Experimental firmware installation on SPIKE Prime and SPIKE Essential via
  usb. The command line commands are unchanged. If you try to install the
  firmware on SPIKE hubs, it will first look for a hub running the regular
  firmware. If it doesn't find any, it will proceed using DFU as before.

## Changed
- Firmware binaries for SPIKE hubs are no longer being customized with a main
  script and a changed checksum. Instead, it simply installs firmware.bin from
  the CI ZIP file.

## [1.0.0-alpha.16] - 2021-10-12

### Added
- Script runner for generic MicroPython boards via USB. This is mainly used for
  debugging.

## Fixed
- Visual Studio Code launcher settings to run a script via BLE.

## [1.0.0-alpha.15] - 2021-09-21

### Added
- Added `VOLUME` to `ble.lwp3.bytecodes.HubProperty` enum.
- Added SPIKE Essential hub device IDs.
- Added Luigi hub device ID.
- 
## Fixed
- Fixed BlueZ disconnecting when sending a command with `pybricksdev lwp3 repl`
  to a City hub.


## [1.0.0-alpha.14] - 2021-08-27

## Changed
- Changed udev rules to use `TAG+="uaccess"` instead of `MODE="0666"`.

## Fixed
- Fixed device not rebooting after `dfu restore`.

## [1.0.0-alpha.13] - 2021-08-06

### Fixed
- Fixed crash in CRC32 checksum.
- Fixed flashing with `dfu-util` not always working ([support#420]).

## [1.0.0-alpha.12] - 2021-08-04

### Changed
- Updated `bleak` dependency to v0.12.1.
- `run` and `compile` scripts now accept `-` as an argument to mean stdin.

### Removed
- Removed script command line args in `run` and `compile` commands. Only accepts
  file name now.

## [1.0.0-alpha.11] - 2021-07-05

### Added
- Added support for Pybricks Protocol v1.1.0.

### Fixed
- Fixed `pybricksdev ble run` not working with BOOST Move hub.

## [1.0.0-alpha.10] - 2021-06-27
### Added
- Support for Python 3.9.
- Short `-n` option for `--name` option in `pybricksdev run`.
- Option to set hub name when flashing firmware.
### Changed
- Update to Bleak v0.12.0.
- Change `pybricksdev run` to use `--wait`/`--no-wait` instead of `--wait=False`.
### Fixed
- Fix `pybricksdev lwp3 repl` can only connect to remote control.
- Fix Technic Large hub Bluetooth hub kind.

## [1.0.0-alpha.9] - 2021-05-27
## Added
- `pybricksdev.ble.lwp3.bytecodes` module.
- `pybricksdev.ble.lwp3.messages` module.
- `pybricksdev lwp3 repl` command line tool.
## Fixed
- Crash when running `pybricksdev dfu` without args on command line.

## [1.0.0-alpha.8] - 2021-05-18
## Added
- `pybricksdev.ble.lwp3` module.
- `pybricksdev.ble.nus` module.
- `pybricksdev.ble.pybricks` module.
## Changed
- Name parameter to `pybricksdev run ble` command is now optional.
## Fixed
- Connecting to BLE devices based on Bluetooth address.

## [1.0.0-alpha.7] - 2021-05-17
## Added
- Debug option to CLI interface.
## Changed
- Use standard Python logging for modules instead of per-object.
- Use progress bars when downloading program to hub.
## Removed
- Delay option in CLI `flash` command.
## Fixed
- Flashing firmware using BLE under conditions on Windows.
- `NotImplementedError` when compiling to .mpy in ipython kernel on Windows.

## 1.0.0-alpha.6
- Skipped for technical reasons.

## [1.0.0-alpha.5] - 2021-05-04
### Added
- REPL installer for SPIKE/MINDSTORMS hubs.
### Fixed
- Data logging to file.

## [1.0.0-alpha.4] - 2021-04-12
### Added
- Size check when restoring firmware via USB/DFU.
- Added `pybricksdev.tools.chunk()` function.
- Added basic command completion to `pybricksdev lwp3 repl`.
### Fixed
- Wait for some time to allow program output to be received before disconnecting
  in the `run` command.
- Fixed spelling of `INPUT` in `pybricksdev.ble.lwp3.messages`.
- Fixed `pybricksdev lwp3 repl` does not exit if device disconnects.

## [1.0.0-alpha.3] - 2021-04-09
### Changed
- Print BLE download progress after chunk is complete instead of before.
### Fixed
- Fix occasional bad checksum warning when running program via BLE.

## [1.0.0-alpha.2] - 2021-04-08
### Added
- Check Pybricks protocol version when connecting to Bluetooth Low Energy devices.
### Fixed
- Fix running programs via Bluetooth Low Energy.

## [1.0.0-alpha.1] - 2021-04-07
### Added
- This changelog.
### Fixed
- DFU flashing not working on Windows.
- Typo in `pip` arguments `README.md`.


<!-- let's try to keep these sorted alphabetically -->
[support#420]: https://github.com/pybricks/support/issues/420

[Unreleased]: https://github.com/pybricks/pybricksdev/compare/v1.0.0-alpha.19..HEAD
[1.0.0-alpha.19]: https://github.com/pybricks/pybricksdev/compare/v1.0.0-alpha.18...v1.0.0-alpha.19
[1.0.0-alpha.18]: https://github.com/pybricks/pybricksdev/compare/v1.0.0-alpha.17...v1.0.0-alpha.18
[1.0.0-alpha.17]: https://github.com/pybricks/pybricksdev/compare/v1.0.0-alpha.16...v1.0.0-alpha.17
[1.0.0-alpha.16]: https://github.com/pybricks/pybricksdev/compare/v1.0.0-alpha.15...v1.0.0-alpha.16
[1.0.0-alpha.15]: https://github.com/pybricks/pybricksdev/compare/v1.0.0-alpha.14...v1.0.0-alpha.15
[1.0.0-alpha.14]: https://github.com/pybricks/pybricksdev/compare/v1.0.0-alpha.13...v1.0.0-alpha.14
[1.0.0-alpha.13]: https://github.com/pybricks/pybricksdev/compare/v1.0.0-alpha.12...v1.0.0-alpha.13
[1.0.0-alpha.12]: https://github.com/pybricks/pybricksdev/compare/v1.0.0-alpha.11...v1.0.0-alpha.12
[1.0.0-alpha.11]: https://github.com/pybricks/pybricksdev/compare/v1.0.0-alpha.10...v1.0.0-alpha.11
[1.0.0-alpha.10]: https://github.com/pybricks/pybricksdev/compare/v1.0.0-alpha.9...v1.0.0-alpha.10
[1.0.0-alpha.9]: https://github.com/pybricks/pybricksdev/compare/v1.0.0-alpha.8...v1.0.0-alpha.9
[1.0.0-alpha.8]: https://github.com/pybricks/pybricksdev/compare/v1.0.0-alpha.7...v1.0.0-alpha.8
[1.0.0-alpha.7]: https://github.com/pybricks/pybricksdev/compare/v1.0.0-alpha.5...v1.0.0-alpha.7
[1.0.0-alpha.5]: https://github.com/pybricks/pybricksdev/compare/v1.0.0-alpha.4...v1.0.0-alpha.5
[1.0.0-alpha.4]: https://github.com/pybricks/pybricksdev/compare/v1.0.0-alpha.3...v1.0.0-alpha.4
[1.0.0-alpha.3]: https://github.com/pybricks/pybricksdev/compare/v1.0.0-alpha.2...v1.0.0-alpha.3
[1.0.0-alpha.2]: https://github.com/pybricks/pybricksdev/compare/v1.0.0-alpha.1...v1.0.0-alpha.2
[1.0.0-alpha.1]: https://github.com/pybricks/pybricksdev/compare/v1.0.0-alpha.0...v1.0.0-alpha.1
