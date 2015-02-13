WAN Failover Script
===================

    forked from https://code.google.com/p/wanfailoverscript/

    WFS checks if your WAN connection is still up by sending ICMP 
    messages to multiple target hosts. It automatically switches 
    between primary and secondary WAN link by changing the default gateway.

Installation

    git clone https://github.com/mysticall/wfs.git
    run the install.sh script.
    edit the configuration /etc/wfs/wfs.conf to your liking
    add target hosts used for testing in /etc/wfs/targets.txt 
    !!! if you do not have a local DNS, use only IP addresses !!!
    edit and copy sample configurations in folder "conf"
    start wfs through "/etc/init.d/wfs start" 


Current network settings

    eth0 - LAN
    IP:  192.168.1.1

    eth1 - WAN1 - PRIMARY interface
    IP:  192.168.5.5
    GW:  192.168.5.1

    eth2 - WAN2 - SECONDARY interface
    IP:  192.168.10.10
    GW:  192.168.10.1


For email notifications (Ubuntu)

    apt-get install mailutils postfix (installs mail and a local MTA)
    configure postfix as an internet gateway
    do not forward an inbound mail to this instance, it should be behind a firewall and
    for outbound notification traffic only.
