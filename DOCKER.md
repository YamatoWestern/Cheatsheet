### Monitor docker

* `docker stats`
* `docker logs <container id>`

### Docker compose

* `docker-compose -f <compose file> up -d --no-deps <container name>`

### Docker prune

* `docker system prune`
* `docker image prune`
* `docker container prune`

### Stop and remove all running docker

```
docker stop $(docker ps -a -q)
docker rm $(docker ps -a -q)
```

[Cheatsheet](https://www.markdownguide.org/cheat-sheet/)
