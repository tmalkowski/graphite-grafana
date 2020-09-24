# graphite + grafana

Volumes will be mapped to directories underneath the CONTAINER_VOLUME_BASEDIR directory.

```sh
env CONTAINER_VOLUME_BASEDIR=$HOME/Library/Docker/Volumes docker-compose up --build -d
```

# ports

- 2003 (carbon receiver)
- 3080 (graphite http api)
- 3081 (grafana http web ui)

# defaults

Default grafana user is 'admin'. Initial password is 'admin', requires reset on first login.


