rancher-gocd-server
=======================

Builds a docker image for gocd server based in rancher-base

To build:

```
docker build -t <registry>/rancher-goserver:<version> .
```

To deploy:

Gocd server: Starts gocd server and configures it

```
docker run -td --name go-server \
-h go-server.${DNS_DOMAIN} \
-v <work-volume> /opt/go-server/work
<registry>/rancher-goserver:<version>

```

To config:

Change and add these env variables to the docker deploy.

```
SERVER_MEM="512m"
SERVER_MAX_MEM="1024m"
SERVER_MAX_PERM_GEN="256m"
SERVER_MIN_PERM_GEN="128m"
GO_SERVER_PORT="8153"
GO_SERVER_SSL_PORT="8154"
SERVER_DIR="$GOCD_HOME"
SERVER_WORK_DIR="$SERVER_DIR"

```
