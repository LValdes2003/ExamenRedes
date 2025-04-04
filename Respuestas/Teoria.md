### Pregunta 1

- Pregunta: ¿Qué representa el mural de las siete capas en términos de las redes de comunicación modernas? Identifica brevemente cada capa y explica cómo se relaciona este antiguo “modelo” con el proceso de comunicación de datos actual.

El mural representa las siete capas del modelo OSI. La primera es la capa física, la cual se encarga de los cables y señales eléctricos. La segunda es la capa de enlace, la cual se encarga de transportar datos dentro de una red con switches usando una dirección MAC. La tercera es la capa de red, la cual se encarga de transportar datos entre redes con routers usando una dirección IP. La cuarta es la capa de transporte, la cual se encarga de transportar los datos usando TCP (Menos rápido, mas seguro) o UDP (Mas rápido, menos seguro). La quinta es la capa de sesión, la cual se encarga de establecer, mantener y terminar una conexión entre dos dispositivos. La sexta es la capa de presentación, la cual se encarga de traducir, codificar, descodificar y comprimir datos de la séptima capa para transmitirlos. La última capa es la séptima, la capa de aplicación. Esta se encarga de conectar las aplicaciones a una red y crear los datos que se transmiten usando DNS y FTP.

### Pregunta 2

- Pregunta: Interpreta los dos rituales descritos. ¿A qué protocolos de comunicación actuales equivalen el mensajero confiable y el mensajero veloz? Compara sus características, explicando las ventajas y desventajas de cada enfoque en redes modernas.

Los rituales refieren a dos protocolos de la capa de transporte: TCP y UDP. El mensajero confiable corresponde a TCP, ya que para establecer y terminar una conexión dos dispositivos necesitan mandar por lo menos tres señales. Además, cada paquete mandado necesita una confirmación del destinatario. El mensajero veloz corresponde a UDP, un protocolo que no averigua si el paquete ha llegado a su destino. Tampoco hay que establecer o terminar una conexión con UDP. Esto hace que UDP sea mas rápido que TCP, ya que los dispositivos necesitan mandar menos que mitad de los paquetes requiridos por TCP. TCP se usa cuando la información necesita estar correcta (texto y archivos), y UDP se usa cuando la transmisión necesita ser rápida (streaming de video y audio).

### Pregunta 3

- Pregunta: Descifra el enigma de la losa. Si la antigua red usaba la dirección 192.168.50.0 como base y necesitaba dividirse en 4 subredes de igual tamaño (una para cada gremio), ¿qué máscara de subred habrían utilizado los antiguos para lograrlo? ¿Cuántas direcciones de host (utilizables) tendría cada subred resultante? Explica brevemente tu razonamiento al calcular la máscara.

La dirección 192.168.50.0 se puede dividir usando la máscara 192.168.50.0/26. La primera subred iría de 0-63, la segunda de 64-127, la tercera de 128-191, y la cuarta de 192-255. Cada red reserva la primera dirección y la última (ej. 0 y 63) para el router y broadcast, así que cada red puede tener 62 hosts.

![Figura 2](/Diagramas/Figura2.png)

### Pregunta 4

- Pregunta: ¿Qué concepto moderno de redes representa el tótem con flechas de la encrucijada? Explica qué es una tabla de enrutamiento y cómo funciona en un router actual. Además, interpreta la diferencia entre las flechas talladas en piedra y las flechas móviles en términos de enrutamiento estático vs. enrutamiento dinámico en redes.

El tótem representa un router, un dispositivo que dirige datos entre dos redes. Cada “aldea” representa una red. Los routers usan tablas de enrutamiento para decidir como mandar un paquete de una dirección IP a otra. Las tablas de enrutamiento contienen la dirección de la red destinaria, la máscara de subred, el próximo salto que ha que hacer para llegar, la interface de donde tiene que salir el paquete y la cantidad mínima de saltos requiridos para llegar. Usando estos datos, el router puede decidir la ruta mas eficiente para que un paquete llegue a su destino. Las flechas talladas en piedra corresponden a enrutamiento estático, donde la ruta no cambia a no sea que un administrador la cambia manualmente. Las flechas móviles corresponden a enrutamiento dinámico, donde la ruta se determina a base de algoritmos, así que si la topología de la red cambia, la tabla de enrutamiento se adapta al cambio, buscando el nuevo camino mas corto. El enrutamiento dinámico permite que el administrador no tenga que cambiar rutas manualmente al introducir un cambio en la red, pero consume mas ancho de banda y es menos seguro que el enrutamiento estático.

### Pregunta 5

- Pregunta: ¿Qué técnica de redes moderna se refleja en la leyenda del Guardián de la Máscara? Nombra y describe brevemente este mecanismo, explicando cómo permite que múltiples dispositivos internos de una red compartan una única identidad (dirección) al comunicarse con el exterior, y menciona dos beneficios que brinda esta estrategia a las redes actuales.

El guardián de la máscara representa NAT (Traducción de Direcciones de Red). Específicamente representa un tipo de NAT dinámico, donde todas las direcciones IP privadas corresponden a solo una dirección IP pública. NAT se usa desde el router, donde los paquetes de cada dispositivo salen de diferentes puertos en el router. De esta manera, al recibir cualquier respuesta al mismo puerto, el router sabe para quien en la red privada es el paquete. Esto significa que no hay que comprar múltiples direcciones de IP públicas, y ofrece un nivel de privacidad, porque dispositivos fuera de la red no saben las dirrecciones IP de los dispositivos dentro de la red.

![Figura 1](/Diagramas/Figura1.png)
