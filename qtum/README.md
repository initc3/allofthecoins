useful commands:
```shell
docker build -t allofthecoins:qtum ./
docker run --name qtum -itd allofthecoins:qtum
docker exec -it qtum src/qtum-cli --version
docker exec -it qtum tail /root/.qtum/debug.log
docker exec -it qtum src/qtum-cli getpeerinfo
docker exec -it qtum bash
```

Runs the qtum node, listens of port 3888 on the host, listens for local RPC connections on 3889

```shell
docker run --name qtum -itd -p 3888:3888 -p 127.0.0.1:3889:3889 -v qtumd-data:/root/.qtum allofthecoins:qtum
```
