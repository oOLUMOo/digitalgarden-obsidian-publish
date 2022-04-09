---
{"dg-publish":true,"permalink":"/linux/ubuntu/basic-configuration/","tags":"gardenEntry"}
---
# Basic configuration
test
## IP config with netpland:

-   Use root user

```bash
sudo u -
```

-   Install htop monitor running process

```bash
apt install htop
```

-   Install ping packet

- Search packet
```bash
apt search iputils
```

- install packet
```bash
apt install iputils-ping
```

-   Generate network card:
```bash
netpland generate
```

-   After configuration has been completed type command:
```bash
netpland apply
```
```bash
release IP:  dhclient -r
```
```bash
renew IP: dhclient -v
```

- Add new network adapter -> after add network adapter for UBUNTU VMs

	- name: name adapter on UBUNTU OS 
		-    click tab -> tab (show name adapters)           
```bash
sudo ip link set <name> up
```
```bash
dhclient <name> -v
```

-   Create new user
```url
https://www.cyberciti.biz/faq/create-a-user-account-on-ubuntu-linux/
```

```bash
useradd -s /bin/bash -m -G sudo <username>
```
```bash
useradd -s /bin/bash -m -G sudo sonvh
```

-   Delete user

```bash
userdel -r template
```

-   Add Network card after install OS

- Check network card
```bash
ip link
```

-   Find your interface (ens192 in my case) and set it to up
```bash
sudo ip link set ens192 up
```

-   Let your interface search an IP Address:
```bash
sudo dhclient ens192 -v
```

-   Edit network static
```bash
network:
	version: 2
	renderer: networkd
	ethernets:
		ens3:
			dhcp4: no
			addresses:
				- 10.1.1.0/24
			gateway4: 10.1.1.254
			nameservers:
				addresses: [10.1.1.200]
```
