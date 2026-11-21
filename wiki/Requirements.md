# Requirements

## Linux

- Docker or Podman
- KVM support
- Hardware virtualization enabled
- At least 2 GB of available RAM
- At least 32 GB of free disk space
- A host with sufficient CPU, RAM, and disk capacity

## Windows

For Docker Desktop or Podman Desktop on Windows 11:

- Windows 11
- Nested virtualization enabled
- At least 2 GB of available RAM
- At least 32 GB of free disk space

Docker Desktop on Windows 10 is not supported for KVM access in this setup.

## macOS

Docker Desktop and Podman Desktop on macOS do not currently provide KVM access to containers.

## Verify KVM on Linux

Install the CPU checker:

```bash
sudo apt install cpu-checker
sudo kvm-ok
```

A working configuration reports:

```text
KVM acceleration can be used
```

Check the device:

```bash
ls -l /dev/kvm
```

Enable Intel VT-x or AMD-V in BIOS or UEFI if KVM is unavailable.
