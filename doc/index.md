# Homelab

Currently, a bare-metal server is used as the basis. It is an [ASRock J5005-ITX](https://www.asrock.com/mb/Intel/J5005-ITX/index.de.asp) with 32GB RAM and two hard disks (1x SSD and 1x HDD).


# Server OS

Install [MicroOS](https://get.opensuse.org/microos/) as MicroOS Container Host. If "PackageKit" is selected instead of "Zypper". If required, the corresponding add-on can also be installed in the Web UI section (cockpit-packagekit).


## Install Web-UI

```shell
transactional-update pkg install cockpit-ws cockpit-system cockpit-bridge cockpit-tukit cockpit-storaged cockpit-podman cockpit-networkmanager
```

Keep in mind that the firewall may already be active. This can be switched off with the following command. 

```shell
systemctl stop firewalld.service
```

## Setup container

```shell
systemctl enable --now podman
```
