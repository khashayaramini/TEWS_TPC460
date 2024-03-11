# Making
- clone the repo
- run `make`

# Testing
- `sudo insmod xr17v35x.ko` to install the module (non persistant)
- `sudo rmmod xr17v35x` to remove the module

# Install
- Edit the `/etc/modules` file and add the name of the module (without the .ko extension) on its own line. On boot, the kernel will try to load all the modules named in this file.
- Copy the module to a suitable folder in `/lib/modules/$(uname -r)/kernel/drivers`. In this case this was `/tty/serial`.
- Run `depmod`. This will find all the dependencies of your module.
- reboot and then run `lsmod | grep module-name` to confirm that the module was loaded at boot.
