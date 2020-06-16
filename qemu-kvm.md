
### from boot disk
https://www.tecmint.com/recover-or-rescue-corrupted-grub-boot-loader-in-centos-7/

### virt-rescue
```sh
sudo yum install libguestfs-tools      # Fedora/RHEL/CentOS
sudo apt-get install libguestfs-tools  # Debian/Ubuntu
guestfish --ro -i -a disk.img
```
http://libguestfs.org/virt-rescue.1.html
virt-rescue [--options] -a disk.img [-a disk.img ...]
http://manpages.ubuntu.com/manpages/xenial/man1/virt-rescue.1.html


virsh list --all

virsh start ubuntu-server

virsh shutdown ubuntu-server


qemu-img resize image.qcow2 +SIZE

Create the new smaller image:
qemu-img create -f qcow2 -o preallocation=metadata newimage.qcow2 NEW_SIZE

Resize the image by copying the old image into the new one.
virt-resize oldimage.qcow2 newimage.qcow2









