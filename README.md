# Proxmox Bootc

Experiment to see if Bootc could work with Proxmox

## Building

In order to get a running proxmox-bootc system you can run the following steps:
```shell
just build-containerfile # This will build the containerfile and all the dependencies you need
just generate-bootable-image # Generates a bootable image for you using bootc!
```

Then you can run the `bootable.img` as your boot disk in your preferred hypervisor.

# Fixes

- `mount /dev/vda2 /sysroot/boot` - You need this to get `bootc status` and other stuff worgkin
- `chmod 777 /var/lock` WORKAROUND
- edit /etc/hosts with your custom host configuration
- `systemctl start pve-cluster.service`
- `systemctl start pve*`
