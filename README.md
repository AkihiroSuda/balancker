# Balancker: poor man's load-balancer for `docker`

Balancker picks up random `$DOCKER_HOST` from ~/.config/balancker

Config (~/.config/balancker):
```
# NOTE: ssh:// requires Docker v18.09 or later
ssh://node1
ssh://node2
# If you are using Docker before v18.09, forward the socket manually with
# `ssh -L` (or set up TLS)
unix:///path/to/docker.sock
```

Random mode:
```console
$ eval $(balancker)
$ docker build -t foo /foo
```

Deterministic mode with seed argument:
```console
$ eval $(balancker bar-seed)
$ docker build -t bar /bar
```
