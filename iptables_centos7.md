# Disable FirewallD
### To disable the FirewallD on your CentOS 7 system, follow these steps:

Type the following command to stop the FirewallD service:
```sh
sudo systemctl stop firewalld
```

Disable the FirewallD service to start automatically on system boot:
```sh
sudo systemctl disable firewalld
```


Mask the FirewallD service to prevent it from being started by another services:
```sh
sudo systemctl mask --now firewalld
```




### Install and Enable Iptables
Perform the following steps to install Iptables on a CentOS 7 system:

Run the following command to install the iptables-service package from the CentOS repositories:
```sh
sudo yum install iptables-services
```


Once the package is installed start the Iptables service:
```sh
sudo systemctl start iptables
sudo systemctl start iptables6
```


Enable the Iptables service to start automatically on system boot:
```sh
sudo systemctl enable iptables
sudo systemctl enable iptables6
```


Check the iptables service status with:
```sh
sudo systemctl status iptables
sudo systemctl status iptables6
```


To check the current iptables rules use the following commands:
```sh
sudo iptables -nvL
sudo iptables6 -nvL
```


By default only the SSH port 22 is open. The output should look something like this:

Chain INPUT (policy ACCEPT 0 packets, 0 bytes)
 pkts bytes target     prot opt in     out     source               destination         
 5400 6736K ACCEPT     all  --  *      *       0.0.0.0/0            0.0.0.0/0            state RELATED,ESTABLISHED
    0     0 ACCEPT     icmp --  *      *       0.0.0.0/0            0.0.0.0/0           
    2   148 ACCEPT     all  --  lo     *       0.0.0.0/0            0.0.0.0/0           
    3   180 ACCEPT     tcp  --  *      *       0.0.0.0/0            0.0.0.0/0            state NEW tcp dpt:22
    0     0 REJECT     all  --  *      *       0.0.0.0/0            0.0.0.0/0            reject-with icmp-host-prohibited

Chain FORWARD (policy ACCEPT 0 packets, 0 bytes)
 pkts bytes target     prot opt in     out     source               destination         
    0     0 REJECT     all  --  *      *       0.0.0.0/0            0.0.0.0/0            reject-with icmp-host-prohibited

Chain OUTPUT (policy ACCEPT 4298 packets, 295K bytes)
 pkts bytes target     prot opt in     out     source               destination     
At this point, you have successfully enabled the iptables service and you can start building your firewall. The changes will persist after a reboot.
