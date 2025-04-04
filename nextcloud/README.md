# Nextcloud

Regain control over your data

<https://nextcloud.com>

## Goals

- more performant than my experiences with nextcloud-aio by linuxserver.io
- as bare-bones as possible. I need a file sync and share service.
- an app only stack. No reverse proxies here.
- data storage outside the stack

## The stack

This is based off the [examples from the Nextcloud community image on GitHub](https://github.com/nextcloud/docker/).

- postgres database
- redis cache
- nextcloud php-fpm app
- ngnix webserver
- cron image

## Environment variables

The Nextcloud docker images support [various environment variables](https://github.com/nextcloud/docker/tree/master?tab=readme-ov-file#auto- wconfiguration-via-environment-variables) that are
passed in to the stack.

This stack will set up and autoinstall from scratch if all variables in
the `example.env` are changed to suit.

Also, sending emails from Nextcloud will be configured if the `SMTP` environment variables are set.

### Extra variables and directories

This stack uses two extra varables:

`NEXTCLOUD_DATA_HOST_DIR`: the directory on the docker host for NextCloud
data. Paired with an internal mapping for `NEXTCLOUD_DATA_DIR` which
brings it outside `${nextcloud-app-container}/var/www/html` to avoid
issues. These issues might well be me holding things wrong, though.

`NEXTCLOUD_APP_DIR`: directory for NextCloud app files. Mapped to  `${nextcloud-app-container}/var/www/html`.

In addition, a database location is defined. Currently, it is set to `${NEXTCLOUD_APP_DIR}-db`, so it lives next to the application data. Issues were encountered during initialization if I placed it inside the container.


## TODO

- set maintenance window to remove the annoying warning
- transition nginx.conf outside the custom docker build and into a volume
- maybe do away with the one-folder-for-db one-folder-for-app nonsense
