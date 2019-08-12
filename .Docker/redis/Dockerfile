FROM redis:latest

LABEL maintainer="maintainer"

#COPY . /usr/src/app
COPY redis.conf /usr/local/etc/redis/redis.conf

VOLUME /data

EXPOSE 6379

CMD [ "redis-server", "/usr/local/etc/redis/redis.conf" ]