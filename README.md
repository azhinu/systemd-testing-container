# Containers with SystemD for Ansible testing

## Installed packages

- bash-completion
- curl
- nano
- netcat
- python3
- sudo
- systemd
- unzip
- wget

## Tags

- latest: Debian 12
- debian: Debian 12
- debian-12: Debian 12

## Run container

⚠️ May not work on Docker Desktop < 4.4.0. Also, old base images (with cgroups v1) will not work without `--cgroupsns=host` flag.

CLI: `docker run --name systemd-debian --privileged -v /sys/fs/cgroup:/sys/fs/cgroup:ro azhinu/systemd:debian-12`

Or use docker compose:

```yaml
version: '3'
services:
  app:
    image: azhinu/systemd:debian-12
    volumes:
      - /sys/fs/cgroup:/sys/fs/cgroup:ro
    privileged: true
```

## Credits

[j8r](https://github.com/j8r/dockerfiles/tree/master/systemd/) - Base Dockerfiles with SystemD

---
 More Dockerfiles can be added later
