# ps5debug

This is a debugger for the PlayStation 5. Yes that's right!

The API is unchanged from `ps4debug`, so `libdebug` should still work.

### :warning: Warnings

ps5debug is currently an experimental beta and not everything works. Please use it with caution.
Please report any issues to the [GoldHEN Discord](https://discord.gg/mpBMcm8n).

### Quickstart Guide
1. Download `Debug Watch` or another debugging tool.
1. Start your favourite jailbreak/exploit.
   - https://github.com/Cryptogenic/PS5-IPV6-Kernel-Exploit.
   - https://github.com/john-tornblom/bdj-sdk.
1. Send the latest version of `ps5debug.elf` to the elf loader's port, typically `9020`.
1. Start your favorite game!
1. Attach to the game (or userland process).
1. Start messing around with your debugging tool, try to find a bug for me!
1. Make l33t hacks.

## Features

- Everything you know and love about ps4debug including:
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
 
## Known Issues

- ASLR is not disabled.
- Todo:
  - `CMD_CONSOLE_INFO`

## Current status with tools

### Reaper Studio
- Debugger works for both ps4/ps5 games.
- Cheat creation is untested.

### MultiTrainer II
- Working with PS4 and PS5 games with some issues:
  - Some code caves that rely on ASLR do not work.
- Patched to work with both types of json cheats, with aslr enabled.
- Fixed version will be released shortly.

### Original Reaper
- Working

### PS4 Cheater
- Working

### Credits

Coded by [ctn123](https://github.com/ctn123) & [SiSTRo](https://github.com/SiSTR0).

Special thanks to:
- [golden](https://github.com/jogolden)
- [Kameleon](https://github.com/kmeps4)

Greeting to other devs:
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

Greeting to QA/Testers:
- [Hejran7](https://www.youtube.com/@BabaAlloush)
