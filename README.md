# docker-base

A base image for Docker containers that uses `supervisord` to manage services.

## Usage

This image does not contain any service because it is thought to be used as base image for other containers.

To use it in your `Dockerfile` just use:

```
FROM odarriba/supervisord:latest
```

## System updates

The image's operating system (Ubuntu 14.04) is **up to date until the day of the last image build.**

## Contributors

* Óscar de Arriba (odarriba@gmail.com)
