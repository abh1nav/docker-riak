# DevDB Riak

Riak v2.0.0 in a docker container - for when you need a quick Riak development node.

## Quickstart

```
docker pull devdb/riak:latest
docker run -d --name riak1 -p 8098:8098 -p 8087:8087 devdb/riak:latest
```

Ping the Riak node using:

```
curl http://localhost:8098/ping
```

and it should return a response of

```
OK
```

Now you can connect to the Riak node using HTTP (on `localhost:8098`) or ProtoBufs (on `localhost:8087`).

**Warning**: The data in Riak is lost when the container is destroyed. If you want the data to persist, then start Riak using:

```
docker pull devdb/riak:latest
docker run -d --name riak1 -p 8098:8098 -p 8087:8087 -v /tmp/riak:/var/lib/riak devdb/riak:latest
```

and Riak in the container will dump the data into `/tmp/riak` on your host machine.
