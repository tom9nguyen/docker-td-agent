Description
===========

Minimalist Dockerfile for running td-agent

Advantages over other fluentd/td-agent Dockerfiles:
- Only runs td-agent; no other random fluentd plugins
- Local copy of GPG key instead of downloading from external HTTP url
- Reads TD api key from environment variable

Usage
=====

    docker build -t pebble/docker-td-agent .
    docker run -p 24224:24224 -e TD_API_KEY=APIKEYGOESHERE pebble/docker-td-agent


Make sure to send incoming requests using `td.[database].[table]` as the tag of your log requests.

See also
========

- [Fluentd Debian installation](http://docs.fluentd.org/articles/install-by-deb)
- [Fluentd to TreasureData](https://docs.treasuredata.com/articles/fluentd-to-treasure-data)
