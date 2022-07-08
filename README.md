# CREATING-INTER-VLAN-SWITCH-AND-ROUT1ER

CREATING INTER-VLAN SWITCH AND ROUTER 
-------------

hostname SW-1
vlan 10
name IT
vlan 20
name HR
vlan 30
name Finance
exit
------

int range fa0/1-2
switchport mode access 
SW-1(config-if-range)#w
switchport access vlan 10
exit
int range fa0/3-4
switchport mode access 
switchport access vlan 20
exit
int range fa0/5-6
switchport mode access 
switchport access vlan 30
exit


inter-vlan switch
------------------
int range fa0/7
SWitchport mode access 
switchport access vlan 10
exit
int fa0/8
switchport mode access 
switchport access vlan 20
SW-1(config-if)#exit
int fa0/9
SW-1(config-if)#sw
switchport mode access 
switchport access vlan 30
exit

inter-vlan router 
------------------
int g0/0
ip address 10.0.0.10 255.255.255.0
no shutdown 
exit
int g0/1
ip address 20.0.0.10 255.255.255.0
Router(config-if)#no shutdown 
exit
int g0/2
ip address 30.0.0.10 255.255.255.0
no shutdown 
exit
