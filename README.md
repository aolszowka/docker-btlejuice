# docker-btlejuice
Docker Image for [btlejuice](https://github.com/DigitalSecurity/btlejuice).

While the official documentation states that you cannot use this in a Docker container[^1], btlejuice/issues/48[^2] states that you cannot use both roles on one machine, which is a slightly different limitation.

For my usage of this project I do not intend to run the Proxy and the Host on the same machine using Docker, rather I am using Docker to avoid installing node and all the other dependencies on my Raspberry Pi instances.

As such there are two containers that differ only in how they are executed:

1. `btlejuice` - This is expected to be the "host" or "console".
2. `btlejuice-proxy` - This is to be deployed on to the proxy machine.


[^1]: From [btlejuice/README.md @  4183c1b](https://raw.githubusercontent.com/DigitalSecurity/btlejuice/4183c1b66b4f65ff1ab442303343efda0dbb52c1/README.md) _BtleJuice Proxy does not work in a Docker container._

[^2]: From [btlejuice#48](https://github.com/DigitalSecurity/btlejuice/issues/48) _Docker containers use the host kernel, so two docker containers have the same host kernel. You're going to run into the same issue as a single machine host. With VMs you have two kernels, so the one physical machine can support multiple adapters._
