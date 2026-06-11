# ShadowNet-Lokinet-i2p-Only-
The lighter version of ShadowNet that implements everything the ShadowNet does but only stripping away the Tor from the route.

This version forces all systemwide connection through Lokinet while still implementing Lokinet/i2p as the cover traffic.

NO TOR!

(This is less secure than the orignal ShadowNet but offers faster browsing)

The only thing that was changed is the systemd-timesyncd. Instead of stopping this and masking this which
would break the i2p, this is now unmasked and started but only after the local loopback establishing and the exceptions.
This ensures that this stays alive and is started long enough for i2p to reach its tunnels but not long enough to hit the physical interface because it will hit the DROP Policy!


how to install:

run sudo bash setup.sh

and then: gcc shadownet.c -o shadownet.c -lm

usages: sudo ./shadownet (start/stop/enable-boot/disable-boot/status-boot)

start: Launches the script

stop: Kills the script and flushes all iptables and reverts changes back to normal

enable-boot: this enables the script to run on boot

disable-boot: this disables thes script to run on boot

statua-boot: checks if it is enabled/disabled to run on boot
