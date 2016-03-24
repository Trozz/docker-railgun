Docker container for CloudFlare Railgun
-----

example docker-compose file
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


** To expand on Docs **
