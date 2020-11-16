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
