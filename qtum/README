useful commands:
```shell
docker build -t allofthecoins:qtum ./
docker run --name qtum -itd allofthecoins:qtum
docker exec -it qtum ./src/qtum-cli getinfo
docker exec -it qtum tail /root/.qtum/debug.log
```

Runs the qtum node, listens of port 8333 on the host, listens for local RPC connections on 8332

```shell
docker run --name qtum -itd -p 8333:8333 -p 127.0.0.1:8332:8332 -v qtumd-data:/root/.qtum allofthecoins:qtum
```
