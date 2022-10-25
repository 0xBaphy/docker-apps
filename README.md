# Docker Apps

## Important steps

1. Clone this repo

```sh
git clone https://github.com/0xBaphy/docker-apps
cd docker-apps
```

2. MACVLAN

Creating a MACVLAN allows us to give each container an individual ip, making management much easier.
You may need to change the `subnet`, `gateway` and `parent` if your network setup differs from mine.

```sh
docker network create -d macvlan \
    --subnet=192.168.1.0/24 \
    --gateway=192.168.1.1 \
    -o parent=eth0 \
    docker-macvlan0
```

3. Caddy

We use caddy as a reverse proxy because of how easy it is to configure using labels inside the `docker-compose` files

```sh
cd caddy
cp ../env.example .env # Don't forget to change the values according to your network setup 
sudo docker-compose up -d
```

## Apps

1. PiHole

Sets up pihole using the MACVLAN network, allowing to use pihole's DHCP feature.

```sh
cd pihole
cp ../env.example .env # Don't forget to change the values according to your network setup
sudo docker-compose up -d
```

2. Media Server

Sets up [Prowlarr](https://prowlarr.com/), [Sonarr](https://sonarr.tv/), [Radarr](https://radarr.video/), [Readarr](https://readarr.com/), [Deluge](https://www.deluge-torrent.org/), [Jellyfin](https://jellyfin.org/), [Jellyseer](https://github.com/Fallenbagel/jellyseerr) and [Organizr](https://github.com/causefx/Organizr) with an individual IP for each service.

```sh
cd media-server
cp ../env.example .env # Don't forget to change the values according to your network setup
sudo docker-compose up -d
```

3. Portainer

Sets up [Portainer CE](https://portainer.io/), a great way to manage your containers

```sh
cd portainer
cp ../env.example .env # Don't forget to change the values according to your network setup
sudo docker-compose up -d
```

4. rtl-sdr-server

Sets up [rtl-sdr](http://git.osmocom.org/rtl-sdr), allowing us to use an [RTL-SDR V3](https://www.rtl-sdr.com) over TCP

```sh
cd rtl-sdr-server
cp ../env.example .env # Don't forget to change the values according to your network setup
sudo docker-compose up -d
```

5. ADS-B Server

Sets up [dump1090](https://github.com/flightaware/dump1090) and [ADS-B Exchange](https://github.com/sdr-enthusiasts/docker-adsbexchange)

```sh
cd ads-b-server
cp ../env.example .env # Don't forget to change the values according to your network setup
sudo docker-compose up -d
```

