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

    /etc/init.d/firewall.sh
    
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
