# Topología

![Figura 3](/Diagramas/Figura3.png)

# Explicación

### Routers

Router llamado Ciudad1 modelo 2911 configurado con ip 10.0.0.1 255.255.255.0 para interface GigabitEthernet0/0 conectado a un switch usando comandos:

```
enable
config t
interface GigabitEthernet0/0
ip address 10.0.0.1 255.255.255.0
no shutdown
exit
```

Y conectado a router Ciudad2 con ip 192.168.30.1 255.255.255.252 para interface Serial0/3/0, usando el módulo HWIC-2T para conectar cable Serial y usando comandos:

```
interface Serial0/3/0
ip address 192.168.30.1 255.255.255.252
no shutdown
exit
```

Router Ciudad2, también modelo 2911, similar a Ciudad1 pero con ips 10.100.100.1 255.255.255.0 y 192.168.30.2 255.255.255.252 usando comandos:

```
interface GigabitEthernet0/0
ip address 10.100.100.1 255.255.255.0
no shutdown
exit
interface Serial0/3/0
ip address 192.168.30.2 255.255.255.252
no shutdown
exit
```

Cada router tiene una tabla de enrutamiento estático con la red del otro, la máscara de esa red y el ip del otro router. Se configura con este comando para Ciudad1:

```
ip route 10.100.100.0 255.255.255.0 192.168.30.2
```

Y para Ciudad2:

```
ip route 10.0.0.0 255.255.255.0 192.168.30.1
```

### PCs

Los PCs se configuran con IPs correspondiendo a su red y su default gateway siendo el IP del router. PC0 tiene ip 10.0.0.2 y gateway 10.0.0.1, PC1 tiene ip 10.0.0.3 y gateway 10.0.0.1, PC2 tiene ip 10.100.100.2 y gateway 10.100.100.1 y PC3 tiene ip 10.100.100.3 y gateway 10.100.100.1. El comando para PC0 es así:

### Switches

Los switches de modelo 2960 no necesitan configuración.
