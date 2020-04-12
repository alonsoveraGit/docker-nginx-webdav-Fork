# docker-nginx-webdav
 Fast Secure and Light Webdav Server

Based on: https://github.com/jbbodart/alpine-nginx-webdav (thanks!)

## How to use this image
```console
$ docker run --name keepass-webdav -p 80:80 -v /path/to/your/keepass/files/:/srv/ -d jbbodart/alpine-nginx-webdav
```

Or use the docker-compose file included.

No built-in TLS support. Reverse proxy with TLS recommended

## Volumes
- `/srv` - served directory

## Authentication
To restrict access to only authorized users (recommended), you can define two environment variables: `$USERNAME` and `$PASSWORD`
```console
$ docker run --name webdav -p 80:80 -v /path/to/your/shared/files/:/srv/ -e USERNAME=webdav -e PASSWORD=webdav -d jbbodart/alpine-nginx-webdav

```