# Commonly used commands

## Transfer files/directories to another server
```
rsync -ahv -e "ssh -i ~/.ssh/lazaro" --progress <SRC_PATH> <DEST>:<DEST_PATH>
```

## Debug Docker networks

Create network graph by running this command and pasting the output into [GraphvizOnline](https://dreampuf.github.io/GraphvizOnline)
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock leoverto/docker-network-graph
```

## Forward remote port via SSH

```
ssh root@server -L local_port:localhost:remote_port -N
```

## Nextcloud logs from Docker container

```
docker exec -it nextcloud bash -c "tail -f /var/www/html/data/nextcloud.log"
```