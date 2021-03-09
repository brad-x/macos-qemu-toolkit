QEMUCTL
===

Purpose
---
A simple script wrapper to make creating, configuring and cloning QEMU VM's easier on macOS.

Create a QEMU VM
---

```bash
$ qemuctl create -disk-size 128G -n Fedora -smp 4 -m 8G -vga std
```

Clone a QEMU VM
---

```bash
$ qemuctl clone -s CentOS-7-Template -d docker-node
```

Start a QEMU VM
---

Initial install with a CDROM drive:

```bash
$ qemuctl start -n Fedora -cdrom ~/ISO/Fedora-Workstation-Live-x86_64-33-1.2.iso
```

Boot your VM with its default configuration:

```bash
$ qemuctl start -n Fedora
```

Boot your VM while customizing the graphics hardware:

```bash
$ qemuctl start -n Gentoo -vga virtio
```

Frequently Asked Questions
---
Q. **What about virtualization framework? Wouldn't it be better to use more of the native facilities?**

A. *Virtualization.Framework is going to be an excellent way to build virtual machine software, but currently it doesn't provide the flexibility QEMU provides out of the box. QEMU takes advantage of the same macOS hypervisor functionality as the framework does, and has a mature set of supported devices that can be configured and customized for use with a virtual machine. As I feel QEMU remains relevant on macOS, I went on to write some scripts to make it manageable.*

Q. **Why not use libvirt on macOS?**

A. *libvirt isn't targeted at macOS and there is a lot of hackery required to get it going and keep it from breaking after an update. I personally aimed at a simple set of scripts to create, configure and launch VM's.*