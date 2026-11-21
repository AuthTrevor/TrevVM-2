# Docker Compose

## Start

```bash
docker compose up -d
```

## View logs

```bash
docker compose logs -f windows
```

## Stop

```bash
docker compose down
```

## Restart

```bash
docker compose restart windows
```

## Default configuration

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
