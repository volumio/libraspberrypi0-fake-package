# libraspberrypi0-fake-package

Fake package for librasperrypi0. This is necessary because libraspberrypi0 depends on packages which mess up the volumio installation (kernel and bootloader) and can't be installed. This results in a dependency hell which prevents packages like libavformat and others from being installed.

## How to create a fake package

```bash
apt-get update
apt-get install -y equivs
apt-cache show libraspberrypi0 > libraspberrypi0.equivs
# Edit the file and remove the dependency line
equivs-build libraspberrypi0.equivs
```
