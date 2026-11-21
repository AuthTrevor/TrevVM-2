# Getting Started

## 1. Install prerequisites

- Docker or Podman
- KVM support on a Linux host
- At least 2 GB of available RAM
- At least 32 GB of free disk space
- Hardware virtualization enabled in BIOS or UEFI

Docker Desktop with nested virtualization is not currently supported for TrevVM-2.

## 2. Create the Compose configuration

Use the repository's existing `compose.yml` or create this file:

```yaml
services:
  windows:
    image: dockurr/windows
    container_name: windows
    environment:
      VERSION: "11"
    devices:
      - /dev/kvm
      - /dev/net/tun
    cap_add:
      - NET_ADMIN
    ports:
      - 8006:8006
      - 3389:3389/tcp
      - 3389:3389/udp
    volumes:
      - ./windows:/storage
    restart: always
    stop_grace_period: 2m
```

## 3. Start TrevVM-2

```bash
docker compose up -d
```

Open:

```text
http://127.0.0.1:8006
```

Wait for Windows installation to finish. The desktop will become available in the web viewer.

## 4. Stop TrevVM-2

```bash
docker compose down
```
