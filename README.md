# reflektor

On the Pi, here's how we landed on running on boot.

* Use `raspi-config` to auto-login your user.

* Add a `startup.sh` to your home directory.

```bash
/usr/bin/cvlc --no-video-title-show --random --loop /home/chris/test.m3u &
```

* Then add that startup script to `.bashrc` with a check to make sure it's only the local user.

```bash
if [ "`tty`" = "/dev/tty1" ]; then
    ./startup.sh
fi
```
