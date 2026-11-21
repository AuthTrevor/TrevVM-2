# Frequently Asked Questions

## How do I use TrevVM-2?

Start the container, open `http://127.0.0.1:8006`, and wait for automatic installation to finish.

## Which Windows version is installed?

Windows 11 Pro is selected by default. Set `VERSION` in Compose to select another supported version.

## Can I resize the virtual disk?

Set `DISK_SIZE`:

```yaml
environment:
  DISK_SIZE: "256G"
```

You may need to extend the Windows disk partition manually.

## Can I share files with the host?

Use a bind mount:

```yaml
volumes:
  - ./example:/shared
```

The folder becomes `Shared` on the Windows desktop and drive `Z:`.

## Can I increase CPU or RAM?

```yaml
environment:
  RAM_SIZE: "8G"
  CPU_CORES: "4"
```

## Can I enable audio?

Set:

```yaml
environment:
  AUDIO: "Y"
```

Then enable **Audio** under **Settings → Advanced** in the web viewer.

## Is the project legal to use?

The project provides open-source tooling, but it does not distribute Windows. You are responsible for obtaining a valid Windows license and complying with Microsoft's licensing terms.
