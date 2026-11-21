# Troubleshooting

## KVM is unavailable

On Linux:

```bash
sudo apt install cpu-checker
sudo kvm-ok
ls -l /dev/kvm
```

Check that:

- Intel VT-x or AMD-V is enabled in BIOS or UEFI.
- Nested virtualization is enabled when the host is a virtual machine.
- Your VPS or cloud provider supports nested virtualization.
- `/dev/kvm` is passed to the container.
- `/dev/net/tun` is accessible.

## Port 8006 does not open

Verify the container is running:

```bash
docker compose ps
docker compose logs -f windows
```

Confirm port 8006 is mapped:

```yaml
ports:
  - "8006:8006"
```

## Installation never completes

Check container logs and the web viewer. Verify that:

- There is enough RAM.
- There is enough free disk space.
- KVM is available.
- The selected Windows version is valid.
- No firewall or proxy is interrupting downloads.

## USB device cannot pass through

Find the device IDs:

```bash
lsusb
```

Then add the device configuration:

```yaml
environment:
  ARGUMENTS: "-device usb-host,vendorid=0x1234,productid=0x1234"
devices:
  - /dev/bus/usb
```

Keep USB mass storage devices disconnected until Windows Setup has finished.
