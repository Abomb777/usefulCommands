Post describes procedure to disable IPv6 on CentOS/RHEL 7. There are 2 ways to do this :
1. Disable IPv6 in kernel module (requires reboot)
2. Disable IPv6 using sysctl settings (no reboot required)

To verify if IPv6 is enabled or not, execute :
```ssh
# ifconfig -a | grep inet6
        inet6 fe80::211:aff:fe6a:9de4  prefixlen 64  scopeid 0x20
        inet6 ::1  prefixlen 128  scopeid 0x10[host]
```
1. Disable IPv6 in kernel module (requires reboot)
1. Edit /etc/default/grub and add ipv6.disable=1 in line GRUB_CMDLINE_LINUX, e.g.:
```ssh
# cat /etc/default/grub
GRUB_TIMEOUT=5
GRUB_DEFAULT=saved
GRUB_DISABLE_SUBMENU=true
GRUB_TERMINAL_OUTPUT="console"
GRUB_CMDLINE_LINUX="ipv6.disable=1 crashkernel=auto rhgb quiet"
GRUB_DISABLE_RECOVERY="true"
```

2. Regenerate a GRUB configuration file and overwrite existing one:
```ssh
# grub2-mkconfig -o /boot/grub2/grub.cfg
```
3. Restart system and verify no line “inet6” in “ip addr show” command output.
```ssh
# shutdown -r now
# ip addr show | grep net6
```

2. Disable IPv6 using sysctl settings (no reboot required)
1. Append below lines in /etc/sysctl.conf:
```ssh
net.ipv6.conf.all.disable_ipv6 = 1
net.ipv6.conf.default.disable_ipv6 = 1
```
NOTE : To disable IPv6 on a single interface add below lines to /etc/sysctl.conf :

net.ipv6.conf.[interface].disable_ipv6 = 1 ### put interface name here [interface]

net.ipv6.conf.default.disable_ipv6 = 1


2. To make the settings affective, execute :
```ssh
# sysctl -p
```
NOTE : make sure the file /etc/ssh/sshd_config contains the line AddressFamily inet to avoid breaking SSH Xforwarding if you are using the sysctl method


3. Add the AddressFamily line to sshd_config :
```ssh
# vi /etc/ssh/sshd_config
```
....
AddressFamily inet
....
Restart sshd for changes to get get effect :
```ssh
# systemctl restart sshd
```
