# agendav-docker

Forked from [nagimov/agendav-docker](https://github.com/nagimov/agendav-docker) and updated to use the latest version of AgenDAV and Debian base image.

Docker image for [AgenDAV - CalDAV web client](https://github.com/agendav/agendav). AgenDAV requires a CalDAV server running alongside (Baïkal, DAViCal, Radicale, etc.). The address of CalDAV server must be specified in `AGENDAV_CALDAV_SERVER` env, e.g. `AGENDAV_CALDAV_SERVER=https://baikal.server.com/cal.php` or `AGENDAV_CALDAV_SERVER=https://radicale.server.svc.com:5232/%u`

## Environment Variables

Note: **all environment variables are mandatory** and must be set via [`docker-compose.yml`](https://github.com/nagimov/agendav-docker/blob/master/docker-compose.yml) or via `-e` option of `docker run ...`. Do not change `AGENDAV_LOG_DIR`, it has to be set to `/var/www/agendav/var/log/`.

| Environment Variable        | Example                               |
| --------------------------- | ------------------------------------- |
| `AGENDAV_SERVER_NAME`       | `127.0.0.1`                           |
| `AGENDAV_TITLE`             | `"Welcome to Example Agendav Server"` |
| `AGENDAV_FOOTER`            | `"Hosted by Example Company"`         |
| `AGENDAV_CALDAV_SERVER`     | `https://baikal.example.com/cal.php`  |
| `AGENDAV_CALDAV_PUBLIC_URL` | `https://baikal.example.com`          |
| [`AGENDAV_TIMEZONE`][phptz] | `America/Denver`, `Europe/Berlin`     |
| `AGENDAV_WEEKSTART`         | `0` (Sunday) or `1` (Monday)          |
| `AGENDAV_LANG`              | `en`                                  |
| `AGENDAV_LOG_DIR`           | `/var/www/agendav/var/log/`           |

## Deployment

Image is available at https://hub.docker.com/repository/docker/dominikl123/agendav/general .

Use the provided [`docker-compose.yml`](https://github.com/dominikl/agendav-docker/blob/master/docker-compose.yml) and deploy via `docker-compose up -d`

AgenDAV will be available at http://localhost . Set up nginx proxy to expose it securely.
