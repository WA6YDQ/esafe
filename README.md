esafe is a bash script to create, mount, unmount and manipulate 
an encrypted filesystem using the cryptsetup program using the luks
linux kernel extentions.

I find it useful, but there are no guarantees as to its usefulness.

For this script, the filesystem is created using /dev/zero and exists
in /root/esafe.bin  or the local directory you are in when esafe is 
started. The default used is the first instance found. This way you can
keep an encrypted filesystem on a flash drive, cd there, and start 
esafe. When the filesystem is first created it will be in /root. You 
can move or copy it around from there.

The size is 250MB, but that can be changed in the create function.

Typing esafe (run as root. use 'sudo' or 'sudo su -') will show the
various options and the filesystem status.

When mounted, the encrypted filesystem will reside on /mnt/container
with permissions 757, owned by root.

Options to esafe are:

on:         enable and mount

off:        disable and unmount

status:     show current status

new:        build a new encrypted filesystem

addkey:	   add an additional key to the filesystem

delkey:     delete an existing key

changekey:  change an existing key

dump:       show encrypted filesystem header info

Warning: deleting the final (only) key will disable
the filesystem with no chance of recovery.

Place the file esafe in /usr/local/bin or where ever you keep your 
executables. Running esafe new will build a new encrypted filesystem.
If your machine does not have /sbin/cryptsetup the esafe script will
use apt-get install to install it. If your machine doesn't use apt-get
you can manually install the cryptsetup programs.

Once the file /root/esafe.bin is fully created it can be copied
as a backup. It can be kept on a usb flash drive.



