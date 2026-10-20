# VAII web server

This repository defines a Docker image with PHP for teaching the VAII course at FRI UNIZA.

Differences from the base [php](https://hub.docker.com/_/php) image:

* `xdebug` installed and configured on port _9003_
* Installed extensions: `pdo_mysql`, `intl`

## Available versions

* `latest` and `main` point to version `8.5`
* `8.4` is based on `php:8.4-apache`
* `8.5` is based on `php:8.5-apache`

### Historical versions (no longer maintained)

* `8.3` is based on `php:8.3-apache`
* `8.2` is based on `php:8.2-apache`

The image is available at `ghcr.io/thevajko/vaii-web-server:latest`. Other versions are available on the [GitHub package](https://github.com/thevajko/vaii-web-server/pkgs/container/vaii-web-server) page.

Docker images are built for the following architectures:

* linux/amd64
* linux/arm64/v8

## Changing the Xdebug port

Xdebug connects to your IDE at `host.docker.internal` on port `9003` by default. If that port is unavailable or your IDE uses a different port, override it with the `XDEBUG_CONFIG` environment variable in your `docker-compose.yml`:

```yaml
services:
  web:
    environment:
      XDEBUG_CONFIG: "client_host=host.docker.internal client_port=9005"
```

Replace `9005` with your preferred port and configure your IDE to listen on the same port. Keep the other settings of your `web` service when adding this environment variable.

Recreate the container to apply the change:

```sh
docker compose up -d --force-recreate web
```
