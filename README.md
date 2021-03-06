Docker container for CloudFlare Railgun
-----
[![Docker Stars](https://img.shields.io/docker/stars/trozz/railgun.svg)]()   [![Docker Pulls](https://img.shields.io/docker/pulls/trozz/railgun.svg)]() 
[![ImageLayers Size](https://img.shields.io/imagelayers/image-size/trozz/railgun/latest.svg)]()   [![ImageLayers Layers](https://img.shields.io/imagelayers/layers/trozz/railgun/latest.svg)]()

You can also find this on [Docker Hub](https://hub.docker.com/r/trozz/railgun/).

## Example

An example `docker-compose.yml` configuration:

```
version: '2'
services:
  railgun:
    image: trozz/railgun
    depends_on:
      - memcache
    links:
      - memcache:memcache
    ports:
      - "2408:2408"
    environment:
      - TOKEN=XXX
      - HOST=1.2.3.4
      - LOG_LEVEL=5
      - MEMCACHED_SERVER=memcache
      - MEMCACHED_PORT=11211
    volumes:
      - /var/log/docker/railgun:/var/log/railgun
  memcache:
    image: memcached
```

## License

BSD Licensed. See LICENSE file for details.
