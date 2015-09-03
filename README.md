# Coco Fleet Unit Healthcheck

Uses fleet api to look at all the units running in the cluster which are in a failed state.

## Building

```
go build -o coco-fleet-unit-healthcheck .

docker build -t coco/coco-fleet-unit-healthcheck .
```

## Running

```
docker run \
    --env FLEET_ENDPOINT=http://localhost:49153 \
    coco/coco-fleet-unit-healthcheck
```

Binary
```
ssh -D 2323 -N core@$FLEETCTL_TUNNEL
./coco-fleet-unit-healthcheck --socks-proxy="localhost:2323" -fleetEndpoint="http://localhost:49153"
```
