# docker-supervisord

A base image for Docker containers that uses `supervisord` to manage services.

## Usage

This image does not contain any service because it is thought to be used as base image for other containers.

To use it in your `Dockerfile` just use:

```
FROM odarriba/supervisord:latest
```

Then you can add new services managed by `supervisord` by creating a file in `/etc/supervisor/conf.d/your_program_name.conf` with something like this:

```
[program:your_program_name]
command=/path/to/your/program
user=user_to_run_program
directory=path/to/run/the/program/from
autostart=true
autorestart=true
stderr_logfile=/path/to/error.log
stdout_logfile=/path/to/console.out.log
```

If your paths and permissions are correct, the program should start as a service the next time you run the container.

If you want to learn more about `supervisord`, you can check this [link](https://www.digitalocean.com/community/tutorials/how-to-install-and-manage-supervisor-on-ubuntu-and-debian-vps)

**Note:** It is very important that your program **must not run in daemon mode.** the reason is that `supervisord` will take this like an exit of the program and will launch it again in loop.
### Running containers using this image
Note that this image `CMD` is the bash console, so you have to run it with `-i -t` params to allow an interactive session.

But if you change the command run at startup, you would probably not have to do this, it is up to you.
## System updates

The image's operating system (Ubuntu 14.04) is **up to date until the day of the last image build.**

## Contributors

* Óscar de Arriba (odarriba@gmail.com)
