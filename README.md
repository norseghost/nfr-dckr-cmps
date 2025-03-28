# nfr-dckr-cmps

*because vowels are lame*

Yet another set of docker compose files for **my** local infrastructure. I
use these for (pseudo)prod. YMMV, use at your own risk.

## Projects

No proxies will be expected to perform in these stacks. I run proxies and
VPNs on edge devices. These supply a web interface.

All stacks communicate on a dedicated docker network, with only the user
facing endpint being bridged.

### Grafana

- alloy
- Prometheus
- Mimir
- Loki
- grafana

### Immich

Photo library, with hardware accelerated object recognition.

### NextCloud

Very basic NextCloud instance. It is self hosted DropBox. No groupware, no
project management, no photo galleries, no office suite.

Hopefully optimized for performance.

### Servarr

Yarr, me mateys!

- sonarr
- radarr
- readarr
- lidarr
- jackett
- recyclarr

- sabnzbd
- qbittorrent

- plex
- overseerr
- jellyfin
