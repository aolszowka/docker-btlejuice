## btlejuice-proxy
This is a docker image that has the [btlejuice](https://github.com/DigitalSecurity/btlejuice) proxy.

This is intended to be deployed on the remote proxying device.

## Usage
To build the image:
```
docker build . --tag btlejuice-proxy:latest
```

To run the container:
```
docker run -d \
      --network=host \
      -e  BTLEJUICE_iface=<Optional Default is hci0> \
      btlejuice-proxy
```
