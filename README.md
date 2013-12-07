debian-firewall-setup
=====================

Script to install and update iptables firewall on Debian.

Usage :

##Installing the script :

Download and move to init folder :

    wget --no-check-certificate https://raw.github.com/benjamin74/debian-firewall-setup/master/firewall.sh
    mv firewall.sh /etc/init.d/firewall.sh
  
Make executable :

    chmod +x /etc/init.d/firewall.sh
  
Edit rules :

    nano /etc/init.d/firewall.sh
    
Example, if you want the server to :

- accept SSH connections on default port 22
- work as a webserver on port 80 and 443 for SSL connections
- work as a proxy on port 3128
- run transmission daemon on port 51413 and the webinterface on port 9091

You must edit the **INCOMING RULES** like this :

    TCP_SERVICES="22 80 443 3128 51413 9091"
    
Example, to allow the server to connect to the internet (to download updates @ upgrades it will use port 80 and 443) you must edit the **OUTGOING RULES** like this :

    REMOTE_TCP_SERVICES="80 443"

##Testing and running the script :
  
Test the rules for 30 seconds :

    /etc/init.d/firewall.sh test

Start the script :

    /etc/init.d/firewall.sh start

Clear / delete all iptables rules set by the script :

    /etc/init.d/firewall.sh clear
    
##Adding script to init scripts :

Add script to default auto-start scripts :

    update-rc.d firewall.sh defaults

Remove it from auto-start scripts :

    update-rc.d -f firewall.sh remove

**Based on :**

http://elliptips.info/guide-debian-7-gerer-le-trafic-entrant-et-sortant-avec-iptables/

http://blog.nicolargo.com/2013/06/ma-methode-pour-gerer-les-regles-iptables.html
