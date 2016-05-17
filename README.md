Warning: this image is wip, it might not works yet

## Notes:
- You must create database schema manually
- Container must run with `--privileged` flag in order to create secure mapped memory, else you must set magma.secure.memory.enable to false


## To start a magma instance:
```shell
docker run -d --name my-magma --privileged --link mysql:mysql --link memcache:memcache -e MYSQL_HOST=mysql -e MYSQL_USER=root -e MYSQL_PASSWORD=root -e MYSQL_SCHEMA=magma magma
```

LINK:
 - a mysql/mariadb container linked
 - a memached container linked with name memache

VOLUME:
- /magma

ENV:
- MYSQL_HOST=mysql
- MYSQL_USER=root
- MYSQL_PASSWORD=root
- MYSQL_SCHEMA=magma

EXPOSE:
- various ports, not configured yet