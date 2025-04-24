# VAII web server

Repozitár slúži na definíciu docker image obsahujúceho PHP pre potreby výučby VAII na FRI UNIZA.

Rozdiely oproti základnému [php](https://hub.docker.com/_/php) image

* Nainštalovaný a nakonfigurovaný `xdebug` na porte _9003_
* Nainštalované moduly: `pdo_mysql`, `intl`

## Dostupné verzie:
* `latest` respektíve `main` odkazuje na verziu `8.3`
* `8.2` založený na `php:8.2-apache`
* `8.3` založený na `php:8.3-apache`

Adresa docker registra `ghcr.io/thevajko/vaii-web-server:latest`, ostatné verzie sú dostupné na [Github package](https://github.com/thevajko/vaii-web-server/pkgs/container/vaii-web-server) stránke.

Docker image sa zostavuje pre nasledovné architektúry:
* linux/386
* linux/amd64
* linux/arm64/v8
* linux/arm/v7
