# zap2xml

See [zap2xml](https://web.archive.org/web/20200426004001/zap2xml.awardspace.info/) for original Perl script and guidance for the configuration file.

## Docker

| Tag | Description |
|---|---|
| latest | Stable zap2xml releases |
| nightly | HEAD zap2xml release |

### Compose

```yaml
services:
  zap2xml:
    image: ghcr.io/jef/zap2xml:latest
    container_name: zap2xml
    restart: unless-stopped
    environment:
      - OPT_ARGS=-I -D -C /config/.zap2xmlrc
      - SLEEPTIME=43200 # 12 hours in seconds
      - TZ=America/Denver
    volumes:
      - ./config:/config
      - ./xmltv:/xmltv

```
