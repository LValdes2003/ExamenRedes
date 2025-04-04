# Topología

![Figura 4](/Diagramas/Figura4.png)

# Explicación

### VLANs

Hay 3 VLANs, VLAN 10 con nombre Arquitectos, VLAN 20 con nombre Politicos y VLAN 30 con nombre Escribas. Cada VLAN tiene dos PCs conectados a dos switches.

### Multilayer Switch

Crear los VLANs con comandos:
```
vlan 10
name Arquitectos
exit
vlan 20
name Politicos
exit
vlan 30
name Escribas
exit
```

Dar IPs a los VLANs y dejar que el switch haga IP routing:

```
ip routing
interface vlan 10
ip address 192.168.10.1 255.255.255.0
exit
interface vlan 20
ip address 192.168.20.1 255.255.255.0
exit
interface vlan 30
ip address 192.168.30.1 255.255.255.0
exit
```

Las interfaces que conectan a otros switches con cables cruzados se hacen trunk ports con el comando:

```
interface range GigabitEthernet1/0/1-2
switchport mode trunk
```

### Switches

Los puertos conectados a PCs se configuran con el VLAN correspondiente. PC0 VLAN 10, PC1 VLAN 20, PC2 VLAN 30, PC3 VLAN 10, PC4 VLAN 20, PC5 VLAN 30. Comandos para Switch1:

```
interface FastEthernet0/2
switchport access vlan 10
exit
interface FastEthernet0/3
switchport access vlan 20
exit
interface FastEthernet0/4
switchport access vlan 30
exit
```

Esto automáticamente crea los VLANs, luego solo hay que poner los nombres con comando name.

### PCs

Cada PC tiene ip correspondiente a su VLAN. PC0 IP 192.168.10.2/24, PC1 IP 192.168.20.2/24 etc.

PCs no pueden hacer ping a PCs en VLANs diferentes, solo a los que tienen el mismo VLAN.
