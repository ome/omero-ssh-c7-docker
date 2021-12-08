omero-ssh-c7
============

[![Actions Status](https://github.com/ome/omero-ssh-c7-docker/workflows/Build/badge.svg)](https://github.com/ome/omero-ssh-c7-docker/actions)


Docker image for testing OMERO on CentOS 7 with systemd.

To get systemd running on Docker additional arguments are required.
Mounting `/sys/fs/cgroup` may be sufficient:

    docker run -d -v /sys/fs/cgroup:/sys/fs/cgroup:ro ... openmicroscopy/omero-ssh-c7

If not, try removing the `:ro` flag:

    docker run -d -v /sys/fs/cgroup:/sys/fs/cgroup ... openmicroscopy/omero-ssh-c7

If all else fails, try running in privileged mode (not recommended):

    docker run -d --privileged ... openmicroscopy/omero-ssh-c7

The Dockerfile creates the `omero` user, password `omero`, with full `sudo` rights. ssh is automatically started via systemd.
