# Remote Desktop

## Web viewer

The web viewer is available at:

```text
http://127.0.0.1:8006
```

It is mainly intended for installation and basic access. RDP generally provides better responsiveness and clipboard support.

## RDP connection

Connect with a Microsoft Remote Desktop client:

| Setting | Value |
|---|---|
| Address | Container IP address or `127.0.0.1` |
| Username | `Docker` |
| Password | `admin` |

## Change credentials

```yaml
environment:
  USERNAME: "bill"
  PASSWORD: "gates"
```

When `DOMAIN` is set, these variables are used as domain credentials.

## Join an Active Directory domain

```yaml
environment:
  DOMAIN: "example.com"
  DOMAIN_OU: "OU=Virtual Machines,OU=Servers,DC=example,DC=com"
```

The host must be able to resolve and reach the domain controller.
