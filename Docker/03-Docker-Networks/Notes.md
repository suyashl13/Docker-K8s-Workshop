# Docker Networking

Docker provides three types of networks: bridge, host, and overlay. Bridge networks are the default network type used by Docker.

## Bridge Networks

Bridge networks use a software bridge to connect containers. This allows containers to access each other and the host machine. Bridge networks are created using the `docker network create` command.

### Pros

* Simple to set up
* Allows containers to access each other
* Allows containers to access the host machine

### Cons

* Limited scalability
* Can be slow due to the overhead of the software bridge

## Host Networks

Host networks allow containers to use the host's network stack. This means that containers can access the host's network interfaces and ports directly. Host networks are created using the `docker network create --driver host` command.

### Pros

* No overhead from a software bridge
* Fast performance

### Cons

* Limited isolation between containers
* Limited control over network configuration

## Overlay Networks

Overlay networks are used to connect multiple Docker daemons together. This allows containers to communicate with each other even if they are running on different hosts. Overlay networks are created using the `docker network create --driver overlay` command.

### Pros

* Allows containers to communicate with each other even if they are running on different hosts
* Provides a high degree of isolation between containers

### Cons

* Requires a key-value store to manage the network state
* Can be complex to set up
