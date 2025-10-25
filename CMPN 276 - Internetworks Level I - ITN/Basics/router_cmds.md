Switch>enable              #Enter privileged EXEC mode 
Switch#configure terminal **or** conf t  #configuration mode

Switch(config)# hostname <hostname>   #to set hostname

S1(config)# enable password c1$c0     #Secure privileged mode access.
S1(config)# exit

S1(config)# line console 0            #set password for console 
S1(config-line)# password letmein
S1(config-line)# login1
S1(config-line)# exit      

S1# show running-config      #   Verify your configuration

S1# config t                            # encrypted password to secure access to privileged mode
S1(config)# enable secret itsasecret
S1(config)# exit

S1# config t                           # Encrypt the enable and console passwords
\S1(config)# service password-encryption
S1(config)# exit


S1# config t                                                               #Configure a MOTD Banner
S1(config)# banner motd "This is a secure system. Authorized Access Only!"
S1(config)# exit

S1# copy running-config startup-config              #Save and Verify Configuration Files to NVRAM

S1# configure terminal


S1(config)# interface vlan 1                                   #configure S1 with an IP address.
S1(config-if)# ip address 192.168.1.253 255.255.255.0
S1(config-if)# no shutdown
 
R1# show flash                   # display flash storage 

R1# copy startup-config flash          # save the startup configuration to flash.

 window

R1(config)# interface gigabitethernet 0/0                        # Configure Router Interfaces
R1(config-if)# ip address 192.168.10.1 255.255.255.0
R1(config-if)# no shutdown

R1(config-if)# description LAN connection to S1                #Configure an interface description that indicates the device to which it is connected

show ip interface brief                 #verification commands to check your interface configurations

show ip route                               #to view the current routing tables




R1(config)# ipv6 unicast-routing                #Enable the router to forward IPv6 packets.

R1(config-if)# ipv6 address 2001:db8:1:1::1/64       #Configure the IPv6 address 
R1(config-if)# ipv6 address fe80::1 link-local       #Configure the link-local IPv6 address
R1# show ipv6 interface brief                        # Verify the addressing configured

R1(config-if)# no ipv6 address 2001:db8:1:5::1/64     #remove the incorrect address
