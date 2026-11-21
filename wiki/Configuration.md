# Configuration

## Select a Windows version

Set the `VERSION` environment variable:

```yaml
environment:
  VERSION: "11"
```

Common values include:

| Value | Version |
|---|---|
| `11` | Windows 11 Pro |
| `11l` | Windows 11 LTSC |
| `11e` | Windows 11 Enterprise |
| `10` | Windows 10 Pro |
| `10l` | Windows 10 LTSC |
| `10e` | Windows 10 Enterprise |
| `2025` | Windows Server 2025 |
| `2022` | Windows Server 2022 |
| `2019` | Windows Server 2019 |
| `2016` | Windows Server 2016 |
| `2012` | Windows Server 2012 |
| `2008` | Windows Server 2008 |
| `7u` | Windows 7 Ultimate |
| `xp` | Windows XP Professional |
| `core11` | Tiny11 Core |
| `tiny11` | Tiny11 |
| `tiny10` | Tiny10 |
| `reactos` | ReactOS |

## Change storage location

```yaml
volumes:
  - ./windows:/storage
```

Replace `./windows` with another folder or named Docker volume.

## Change disk size

```yaml
environment:
  DISK_SIZE: "256G"
```

The default disk size is 64 GB. Increasing the size of an existing disk may require manually extending the Windows partition.

## Set CPU and RAM

```yaml
environment:
  RAM_SIZE: "8G"
  CPU_CORES: "4"
```

Defaults are 2 CPU cores and 4 GB of RAM.

## Share files

```yaml
volumes:
  - ./example:/shared
```

The folder appears as `Shared` on the Windows desktop and as drive `Z:`.

## Use a custom ISO

```yaml
environment:
  VERSION: "https://example.com/windows.iso"
```

Alternatively, bind a local ISO:

```yaml
volumes:
  - ./example.iso:/custom.iso
```

## Run a command after installation

```yaml
environment:
  COMMAND: 'reg add "HKLM\Software\Example" /v Enabled /t REG_DWORD /d 1 /f'
```
