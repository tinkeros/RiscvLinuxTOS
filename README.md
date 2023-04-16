# RiscvLinuxTOS

Riscv Emulator running Linux on TinkerOS/ZealOS

### Files description:
- `*.HC` HolyC files, use these to run on TinkerOS.
- `*.ZC` Files to run on ZealOS instead.
- `loader_64.bin` - RISC-V Linux kernel + root filesystem binary blob (see <a href="https://github.com/franzflasch/linux_for_riscv_em">here</a> for building).
- `riscv_em.dtb` - Binary device tree passed to kernel (<a href="https://github.com/franzflasch/riscv_em">see this for building</a>).
- `riscv_em.prg` - A compiled binary blob composed of a modifed version of riscv_em (see <a href="https://github.com/franzflasch/riscv_em/commit/3e60d1ce7afcbe96ae21a827a0ce83a5a5afa924">here</a> for changes from original) and a modified uClibc library (see <a href="https://github.com/jwhitham/frotz">here</a> for changes).  This is built using a custom toolchain and built to interface with a custom kernel shim layer that translates Linux ABIs and syscalls to TempleOS ABIs and kernel functions (since TOS has no syscalls).  It is sort of like WINE, it is not an emulator, it runs Linux compiled machine code on TOS.  For those interested, <a href="https://minexew.github.io/2020/05/10/templeos-loader-part3.html">this blog</a> provides a good overview of the difference between the Linux and TempleOS ABIs.  Building this properly is a complex process beyond the scope of this document.

Don't expect to do anything useful with this, I made it for fun, mostly just so I could simply say I booted Linux on TempleOS/TinkerOS/ZealOS.

You do not have real a terminal/tty so don't expect interactive commands to work, but non-interactive text applications and shell commands should work fine.

There is no support for graphics, networking, or access to the host TinkerOS/ZealOS filesystem.  The only things you can access are things on the pre-built root filesystem.
