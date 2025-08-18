### Demonstrating Docker Networking Commands.

> ***Simple Exercise:*** Will create a new docker network. Attach two containers to it and will ping each other inside both of them.

1. Creating a new docker network.
```bash
$ docker network create my-bridge-network
```

2. Running a container and attaching it to the new network.
```bash
$ docker run -d --name container1 --network my-bridge-network nginx
$ docker run -d --name container2 --network my-bridge-network alpine sleep 1000
```

3. Pinging each other inside both of them.
```bash
$ docker exec container1 ping container2
```

<hr />

#### Results 
```bash
$ docker exec -it container2 ping container1
PING container1 (172.18.0.2): 56 data bytes
64 bytes from 172.18.0.2: seq=0 ttl=64 time=0.082 ms
64 bytes from 172.18.0.2: seq=1 ttl=64 time=0.244 ms
64 bytes from 172.18.0.2: seq=2 ttl=64 time=0.148 ms
64 bytes from 172.18.0.2: seq=3 ttl=64 time=0.230 ms
64 bytes from 172.18.0.2: seq=4 ttl=64 time=0.223 ms
64 bytes from 172.18.0.2: seq=5 ttl=64 time=0.214 ms
64 bytes from 172.18.0.2: seq=6 ttl=64 time=0.150 ms
64 bytes from 172.18.0.2: seq=7 ttl=64 time=0.293 ms
64 bytes from 172.18.0.2: seq=8 ttl=64 time=0.237 ms
64 bytes from 172.18.0.2: seq=9 ttl=64 time=0.181 ms
64 bytes from 172.18.0.2: seq=10 ttl=64 time=0.226 ms
¸64 bytes from 172.18.0.2: seq=11 ttl=64 time=0.102 ms
```