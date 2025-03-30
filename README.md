# ps5debug
```
              ____      _      _
    _ __  ___| ___|  __| | ___| |__  _   _  __ _
   | '_ \/ __|___ \ / _` |/ _ \ '_ \| | | |/ _` |
   | |_) \__ \___) | (_| |  __/ |_) | |_| | (_| |
   | .__/|___/____/ \__,_|\___|_.__/ \__,_|\__, |
   |_|                                     |___/
               Coded by Ctn & SiSTRo.

```

This is a debugger for the PlayStation 5. Yes that's right!

The API is unchanged from `ps4debug`, so `libdebug` should still work.

Latest version: `v1.0b3`

### :warning: Warnings

ps5debug is currently an experimental beta and not everything works. Please use it with caution.
Please report any issues to the [GoldHEN Discord](https://discord.gg/pR5NTEVBGt).

### Quickstart Guide
1. Download `Debug Watch` or another debugging tool.
1. Start your favourite jailbreak/exploit.
   - https://github.com/Cryptogenic/PS5-IPV6-Kernel-Exploit.
   - https://github.com/PS5Dev/PS5-UMTX-Jailbreak
   - https://github.com/john-tornblom/bdj-sdk.
1. Send the latest version of `ps5debug.elf` to the elf loader's port, typically `9020`.
1. Start your favorite game!
1. Attach to the game (or userland process).
1. Start messing around with your debugging tool, try to find a bug for me!
1. Make l33t hacks.

## Features

- Everything you know and love about ps4debug including:
  - Firmware supported: (*) means untested
    - `3.xx`,
    - `4.xx`,
    - `5.xx`,
  - Rest mode support.
  - Console scanner.
  - `klog` server on port `3232`.
- New API command(s):
  - `CMD_PROC_BASE`(`0xBDAA000D`) - Gets the base address of the executable section.
    ```
    struct cmd_proc_base_packet {
        uint32_t pid;
    } __attribute__((packed));

    struct cmd_proc_base_response {
        uint64_t address;
    } __attribute__((packed));
    ```
  - `CMD_CONSOLE_VERSION`(`0xBD000502`) - Returns 4 for PS5 and 5 for PS5.
    ```
    struct cmd_proc_console_version_packet {
        uint32_t pid;
    } __attribute__((packed));

    struct cmd_proc_console_version_packet_response {
        uint16_t address;
    } __attribute__((packed));
    ```

## Known Issues

- ASLR is not disabled.


## Current status with tools

### Reaper Studio - Debugger, Trainer creator.
- Working.

### MultiTrainer II - Cheat/Trainer Loader
- Working

### Original Reaper - Debugger, Trainer creater.
- Working

### PS4 Cheater - Memory scanner/viewer.
- Working

### Credits

Coded by [ctn123](https://github.com/ctn123) & [SiSTRo](https://github.com/SiSTR0).

Special thanks to:
- [golden](https://github.com/jogolden)
- [Kameleon](https://github.com/kmeps4)

Greeting to other devs: (alphabetical order)
- [Al-Azif](https://github.com/Al-Azif)
- [ChendoChap](https://github.com/ChendoChap)
- [flat_z](https://github.com/flatz)
- [idc](https://github.com/idc)
- [kiwidoggie](https://github.com/kiwidoggie)
- [qwertyoruiop](https://twitter.com/qwertyoruiopz)
- [sleirsgoevy](https://github.com/sleirsgoevy)
- [Specter](https://github.com/Cryptogenic)
- [SocraticBliss](https://github.com/SocraticBliss)
- [theflow0](https://github.com/TheOfficialFloW)
- [Vortex](https://github.com/xvortex)
- [zecoxao](https://twitter.com/notzecoxao)
- [Znullptr](https://github.com/dmiller423)

Greeting to QA/Testers: (alphabetical order)
- [Big_Wadger](https://twitter.com/big_wadger)
- d01v
- [Echo Stretch](https://twitter.com/StretchEcho)
- [Hejran7](https://www.youtube.com/@BabaAlloush)
- [Pharaoh2k](https://github.com/Pharaoh2k)

### Changelog:
- v1.0b1
  - initial release
- v1.0b2
  - Fixed attach/detach issue when game exits during a debug session.
  - Improved support for debugging multi-threaded processes.
  - Improved allocations for cheats.
  - General stability improvements.
  - General Performance improvements.
  - Added support for 5.xx
  - Added support for 9021 elf loader.
  - Implemented hardware breakpoints.
  - Optimisations for kstuff.
- v1.0b3
  - Added support for 5.xx kdata offset change.

