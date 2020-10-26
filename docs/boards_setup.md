# Setting up the boards

Depending on the board used and the linux distribution available for your board some steps may vary.

---

## Burning SD cards :cd:

Since there are a lot of tutorials on how to do this I can just only point you to the one I followed and it works on all boards I have used. [Raspberry Pi Installing Images](https://www.raspberrypi.org/documentation/installation/installing-images/)

---

## Connection and power :electric_plug:

- Connect the switch to the network and the boards to the switch.
- Power up the boards and the switch.

---

## Finding your boards :mag:

To find the IP assigned to the boards by the DHCP server on the router you can use nmap.

```shell
nmap -sT 192.168.0.1/24
```

There are other tools that can also work like the ones listed below.

- [Angry IP Scanner](https://angryip.org/).

---

## Final step on preparation

### Log into each board

In order to do changes on each board we need to SSH into them to make some changes. To do so we can access them by executing `ssh root@192.168.0.110`.

### Static IP Address

I setup the static IP address on each board using `armbian-config`

### Setting hostname (Optional)

For this I also used `armbian-config` but in all debian distributions the steps are the following:

- Set the hostname
  ```shell
  sudo hostnamectl set-hostname master_node
  ```
- Edit the `/etc/hosts` file.

  ```shell
  127.0.0.1   localhost
  127.0.0.1   master_node

  # The following lines are desirable for IPv6 capable hosts
  ::1     localhost ip6-localhost ip6-loopback
  ff02::1 ip6-allnodes
  ff02::2 ip6-allrouters
  ```

- Check changes.

  ```shell
  hostnamectl
  ```
