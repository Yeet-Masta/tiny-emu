# RISCV-EMU

This is a community build of [TinyEMU][tinyemu], targeting in GNU/Linux, macOS,
and MS-Windows support.

[tinyemu]: https://bellard.org/tinyemu/

## Features

- 32/64/128-bit RISC-V emulation.
- VirtIO console, network, block device, input and 9P filesystem.
- Framebuffer emulation through SDL.
- Support for loading ELF images.
- Support for loading initrd images or compressed initramfs archives.
- Remote HTTP block device and filesystem.
- Small code, easy to modify, no external dependencies.

## Usage

Use the VM images available from Fabrice Bellard's [jslinux][] (no need to download them):

```shell
$ ./temu https://bellard.org/jslinux/buildroot-riscv64.cfg

Welcome to JS/Linux (riscv64)

Use 'vflogin username' to connect to your account.
You can create a new account at https://vfsync.org/signup .
Use 'export_file filename' to export a file to your computer.
Imported files are written to the home directory.

[root@localhost ~]# uname -a
Linux localhost 4.15.0-00049-ga3b1e7a-dirty #11 Thu Nov 8 20:30:26 CET 2018 riscv64 GNU/Linux
[root@localhost ~]#
```

Use `C-a x` to exit the emulator.

You can also use TinyEMU with local configuration and disks. You can find more information in Fabrice Bellard's [documentation for TinyEMU][tinyemu-readme].

[jslinux]: https://bellard.org/jslinux
[tinyemu-readme]: https://bellard.org/tinyemu/readme.txt

## Installing

If you're compiling from source, you'll need:

- [OpenSSL][] (optional)
- [SDL 2.0][sdl] (optional)

[openssl]: https://www.openssl.org
[sdl]: https://www.libsdl.org

Make sure to disable `CONFIG_INT128` for 32-bit hosts.

## Credits

TinyEMU was created by [Fabrice Bellard][fabrice], and Fernando Lemos improved its macOS support.

[fabrice]: https://bellard.org

## License

TinyEMU is released under the MIT license unless otherwise specified in specific files.

The SLIRP library has its own license (two-clause BSD license).
