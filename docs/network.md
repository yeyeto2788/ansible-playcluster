# Network

Since I didn't want to spend too much money on the build in order to start testing ansible and kubernetes I used the hardware described on the [./hardware.md] document.

So given that I use only 3 single board computers here is how the network looks

<div style="text-align:center"><img src="./docs/images/network_diagram.png" width="300"/></div>

## IP Addresses

I assign a static IP address on each board using the `armbian-config` tool which made the process much easier, but you can also do it from your router's configuration.

This are the IP address I setup on my network.

| Board |  IP Address   |  Node type   | Board             |
| :---: | :-----------: | :----------: | :---------------- |
| SBC1  | 192.168.0.110 | control node | Orange Pi PC Plus |
| SBC2  | 192.168.0.111 | worker node  | Orange Pi One     |
| SBC3  | 192.168.0.112 | worker node  | Orange Pi PC      |
