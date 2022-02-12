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


## Optional Arguments
For my purposes I am running this on a Raspberry Pi 3B to perform the capture (with the Host/Console on a Raspberry Pi 4B), according to btlejuice/issues/35[^1] the BLE Adapter that ships on the RPi is not compatible with [nobel/bleno](https://github.com/noble/bleno)[^2] this results unexpected behavior[^3]. For my purposes I am utilizing an ASUS BT-400 which is listed as supported, however when using this on the RPi this shows as `hci1`. `btlejuice-proxy` supports this with an optional argument of `--iface`; therefore, the Docker pass through variable `BTLEJUICE_iface` was created to support this.

[^1]: From [btlejuice#35](https://github.com/DigitalSecurity/btlejuice/issues/35) _I've already met this error, and the reason is quite simple: the BLE adapter you are using is not compatible with Noble/Bleno._
[^2]: This appears to be a limitation of [noble/node-bluetooth-hci-socket](https://github.com/noble/node-bluetooth-hci-socket) from [nobel/node-bluetooth-hci-socket/README.md @ 15c6eef](https://github.com/noble/node-bluetooth-hci-socket/blob/15c6eef5731ec4cdbf9ca4af7b2e3b42d9e62fdf/README.md) under _Compatible  Bluetooth 4.0 USB Adapters_
[^3]: Sometimes this results in a `RangeError: index out of range` inside of `BluetoothHciSocket`, and other times it just results in the console constantly spinning.
