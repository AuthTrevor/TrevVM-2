# Docker CLI

## Run the container

```bash
docker run -it --rm \
  --name windows \
  -e "VERSION=11" \
  -p 8006:8006 \
  --device=/dev/kvm \
  --device=/dev/net/tun \
  --cap-add NET_ADMIN \
  -v "${PWD}/windows:/storage" \
  --stop-timeout 120 \
  dockurr/windows
```

## Access the web viewer

Open:

```text
http://127.0.0.1:8006
```

## Stop the container

```bash
docker stop windows
```

## Remove the container

```bash
docker rm windows
```
