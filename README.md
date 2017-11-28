# BBC Archive Development base package

This package contains common scripts and configuration shared across all
Archive Development instances (real hardware, VMs, sandboxes, etc.) and
all environments.

## Docker images

The [docker](docker) directory contains the `Dockerfiles` needed to build
 `bbcarchdev-base`  [Docker images](https://hub.docker.com/r/bbcarchdev/bbcarchdev-base/)
 for the three environments that we use: `live`, `stage` and `dev`. 
 
 You can pull these images with:

    $ docker pull bbcarchdev/bbcarchdev-base:ENV

For example:

    $ docker pull bbcarchdev/bbcarchdev-base:live

If in doubt, use `live`.
