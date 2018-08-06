# cratedb cluster setup demo

> with docker && docker-compose

## How to Run

```code
docker-compose up -d
```

## search result

> you can use pg client connect to the server(user is crate)

```code
select count(*) from sys.nodes
```

## some notes

* vm.max\_map\_count

```code
CrateDB requires [vm.max_map_count to be at least 262166](https://crate.io/docs/reference/en/latest/configuration.html#virtual-memory).  You will get an error on startup if it is less.  This is set using a container init in the pod definition.

do like below:

echo  vm.max_map_count=655360 >> /etc/sysctl.conf && \
sysctl -p

```
