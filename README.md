# Updated Xpad Linux Kernel Driver
Driver for the Xbox/ Xbox 360/ Xbox 360 Wireless/ Xbox One Controllers

## Changes compared to Linux Staging
* fixed blinking LED on Xbox 360 Wireless Controllers (based on [SteamOS Version](https://github.com/ValveSoftware/steamos_kernel/commit/d92cfaac03183c01382bde7e817d22e4ea9078d5))
* fixed kernel panics due to URB request races ([patch by Sarah Bessmer](https://www.marc.info/?l=linux-input&m=140023068527280&w=2))
* merged Xbox One controller force feedback (again from SteamOS)

# Installation
```
sudo git clone https://github.com/paroj/xpad.git /usr/src/xpad-0.4
sudo dkms install -m xpad -v 0.4
```
# Updating
```
cd /usr/src/xpad-0.4
sudo git fetch
sudo git checkout origin/master
sudo dkms remove -m xpad -v 0.4 --all
sudo dkms install -m xpad -v 0.4
```

# Merging Upstream
if you are the lazy kernel input maintainer who has neither merged nor replied to Sarahs patches before, you can do now. The commits are properly documented and have the right author field. Just run `git format-patch staging..master`.
