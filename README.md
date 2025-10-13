# Multiarch container images for acme-dns

![Build Status](https://github.com/Glopix/acme-dns-multiarch/actions/workflows/build.yml/badge.svg)

This repository automatically checks for new [acme-dns](https://github.com/joohoi/acme-dns) releases every 2 days and builds multi-architecture container images for:
- `linux/amd64`
- `linux/arm/v6`
- `linux/arm/v7`
- `linux/arm64/v8`

In other words: for Raspberry Pi and similar systems.

## Images
Find published images on [Docker Hub](https://hub.docker.com/repository/docker/glopix/acme-dns-multiarch).

## Usage example
Pull the latest image:

```sh
docker pull glopix/acme-dns-multiarch:latest
```

Run the container (example):

```sh
docker run --rm --name acmedns                 \
 -p 53:53                                      \
 -p 53:53/udp                                  \
 -p 80:80                                      \
 -v /path/to/your/config:/etc/acme-dns:ro      \
 -v /path/to/your/data:/var/lib/acme-dns       \
 -d glopix/acme-dns-multiarch
```

For configuration and more details, see the [acme-dns documentation](https://github.com/joohoi/acme-dns).

## Credits
Many thanks to [@joohoi](https://github.com/joohoi) for his excellent work on the acme-dns project!

