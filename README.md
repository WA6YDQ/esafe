esafe is a bash script to create, mount, unmount and manipulate 
an encrypted filesystem using the cryptsetup program using the luks
linux kernel extentions.

I find it useful, but there are no guarentees as to its usefulness.

For this script, the filesystem is created using /dev/zero and exists
in /root/esafe.bin 

The size is 250MB.

Typing esafe (run as root - use sudo or sudo su -) will show the
various options and the filesystem status.

When mounted, the encrypted filesystem will reside on /mnt/container
with permissions 757, owned by root.

Options to esafe are:
on         enable and mount
off        disable and unmount
status     show current status
new        build a new encrypted filesystem
addkey	   add an additional key to the filesystem
delkey     delete an existing key
changekey  change an existing key
dump       show encrypted filesystem header info

Warning: deleting the final (only) key will disable
the filesystem with no chance of recovery.


