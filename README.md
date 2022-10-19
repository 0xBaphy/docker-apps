# Docker Apps

## Pi Hole

Sets up pihole using a MACVLAN network, allowing to use pihole's DHCP feature.

Copy `env.example` to `.env` and change the values according to your set up, then run `sudo docker-compose up`.

## Media Server

Sets up [Prowlarr](https://prowlarr.com/), [Sonarr](https://sonarr.tv/), [Radarr](https://radarr.video/), [Readarr](https://readarr.com/), [Deluge](https://www.deluge-torrent.org/), [Jellyfin](https://jellyfin.org/), [Jellyseer](https://github.com/Fallenbagel/jellyseerr) and [Organizr](https://github.com/causefx/Organizr) with an individual IP for each service.

Copy `env.example` to `.env` and change the values according to your set up, then run `sudo docker-compose up`.
