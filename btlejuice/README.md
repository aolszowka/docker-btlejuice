## docker-btlejuice
This is a docker image that has the [btlejuice](https://github.com/DigitalSecurity/btlejuice) host/console.

## Usage
To build the image:
```
docker build . --tag btlejuice:latest
```

To run the container:
```
docker run --network=host -e BTLEJUICE_ProxyAddress=IP.Address.In.Here btlejuice
```
