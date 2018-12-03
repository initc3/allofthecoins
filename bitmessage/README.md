useful commands:
```shell
docker build -t allofthecoins:bitmessage ./
docker run --name bitmessage -itd allofthecoins:bitmessage
docker exec -it bitmessage bash
docker exec -it bitmessage python src/bitmessagemain.py
```
