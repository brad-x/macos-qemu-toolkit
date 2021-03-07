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