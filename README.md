# docker-supervisord

A base image for Docker containers that uses `supervisord` to manage services.

## Usage

This image does not contain any service because it is thought to be used as base image for other containers.

To use it in your `Dockerfile` just use:

```
FROM odarriba/base:latest
```

Then you can add new services managed by `supervisord` by creating a file in `/etc/supervisor/conf.d/your_program_name.conf` with something like this:

```
[program:your_program_name]
command=/path/to/your/program
autostart=true
autorestart=true
stderr_logfile=/path/to/error.log
stdout_logfile=/path/to/console.out.log
```

If you want to learn more about `supervisord`, you can check this [link](https://www.digitalocean.com/community/tutorials/how-to-install-and-manage-supervisor-on-ubuntu-and-debian-vps)
## System updates

The image's operating system (Ubuntu 14.04) is **up to date until the day of the last image build.**

## Contributors

* Óscar de Arriba (odarriba@gmail.com)
