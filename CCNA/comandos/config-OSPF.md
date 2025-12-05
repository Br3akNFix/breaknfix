+++
title = "Configuración OSPF"
date = 2025-08-22
+++

#### Configuración de OSPF (Open Shortest Path First)

En esta sección encontrarás los comandos más importantes para **configurar, ajustar y verificar OSPF** en routers Cisco.  
Cada comando viene acompañado de una breve explicación para entender qué hace.

```bash
R1(config)# router ospf 1
```

Inicia el proceso OSPF en el router. El `process-id` solo tiene significado local, no debe coincidir con otros routers.

```bash
R1(config-router)# network 10.0.12.0 0.0.0.3 area 0
```

Activa OSPF en una interfaz si su dirección IP coincide con la red indicada, y la asocia a un área.

```bash
R1(config-router)# router-id 1.1.1.1
```

Define manualmente el Router ID, valor único que identifica al router dentro del dominio OSPF.

```bash
R1(config-router)# clear ip ospf process
```

Reinicia el proceso OSPF. Necesario para aplicar cambios en el Router ID.

📊 Métrica (Cost)

```bash
R1(config-if)# ip ospf cost 10
```

Ajusta manualmente el costo de la interfaz (métrica usada para calcular rutas).

```bash
R1(config-router)# auto-cost reference-bandwidth 10000
```

Cambia el ancho de banda de referencia global (por defecto 100 Mbps). Importante en redes rápidas (Gigabit o superiores).

🔒 Passive Interface

```bash
R1(config-router)# passive-interface g1/0
```

Evita que OSPF envíe mensajes Hello por esa interfaz, pero la red aún será anunciada en OSPF.

```bash
R1(config-router)# passive-interface default
```

Pone **todas** las interfaces en modo pasivo.

```bash
R1(config-router)# no passive-interface g0/0
```

Reactiva OSPF en una interfaz específica.

🌍 Ruta por Defecto

```bash
R1(config-router)# default-information originate
```

Redistribuye una ruta por defecto en OSPF. Convierte al router en un ASBR (Autonomous System Boundary Router).

🌐 Tipo de Red OSPF

```bash
R1(config-if)# ip ospf network {broadcast | non-broadcast | point-to-multipoint | point-to-point}
```

Define el tipo de red OSPF en una interfaz. Esto afecta cómo se forman los vecinos y si se eligen DR/BDR.

**Comandos sh**

```bash
R1# show ip ospf neighbor
```

👉 Muestra los vecinos OSPF y su estado de adyacencia.

```bash
R1# show ip protocols
```

👉 Verifica información general de OSPF, incluyendo Router ID, timers y redes anunciadas.

```bash
R1# show ip ospf database
```

👉 Muestra la LSDB (Link State Database), incluyendo los LSAs recibidos.

```bash
R1# show ip route ospf
```

👉 Visualiza las rutas instaladas en la tabla de enrutamiento vía OSPF.




