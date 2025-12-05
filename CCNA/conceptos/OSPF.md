



# OSPF (Open Shortest Path First) - Routing Básico

## 1. Introducción
OSPF es un protocolo de enrutamiento dinámico de tipo **link-state**.  
Permite que los routers intercambien información sobre la topología de la red y calculen la mejor ruta usando el algoritmo de Dijkstra.  
Es ampliamente usado en redes empresariales y es parte esencial del examen CCNA.



## 2. Conceptos clave
- **Tipo de protocolo:** Link-state.  
- **Algoritmo:** Dijkstra (SPF - Shortest Path First).  
- **Áreas:** Segmentos lógicos de la red OSPF (ej. Área 0 como backbone).  
- **LSA (Link-State Advertisements):** Mensajes que describen la topología.  
- **DR/BDR:** Designated Router y Backup Designated Router en redes multiacceso.  
- **Coste:** Métrica basada en el ancho de banda del enlace.  



## 3. Explicación detallada

### 3.1 Ventajas de OSPF
- Convergencia rápida.  
- Escalabilidad en redes grandes.  
- Soporte para VLSM y CIDR.  
- Menor uso de ancho de banda comparado con RIP.  

### 3.2 Áreas en OSPF
- **Área 0 (Backbone):** Todas las demás áreas deben conectarse a ella.  
- **Áreas adicionales:** Permiten dividir la red para optimizar rendimiento.  

### 3.3 DR y BDR
- En redes multiacceso (ej. Ethernet), OSPF elige un **DR** y un **BDR** para reducir el tráfico de LSAs.  


## 4. Comandos y configuraciones

### Habilitar OSPF en un router

```bash
Router> enable
Router# configure terminal
Router(config)# router ospf 1
Router(config-router)# network 192.168.1.0 0.0.0.255 area 0
```

### Configurar múltiples redes en OSPF
```bash
Router(config-router)# network 10.0.0.0 0.0.0.255 area 0
Router(config-router)# network 172.16.0.0 0.0.255.255 area 1
```

### Verificar configuración
```bash
Router# show ip ospf neighbor
Router# show ip route ospf
Router# show ip protocols
```

---

## 5. Ejercicios prácticos
- [ ] Configura OSPF en dos routers y verifica la tabla de enrutamiento.  
- [ ] Divide la red en dos áreas (0 y 1) y comprueba la conectividad.  
- [ ] Identifica el DR y BDR en una red multiacceso con tres routers.  
- [ ] Usa `show ip ospf neighbor` para verificar la formación de adyacencias.  

---

## 6. Resumen del tema
- OSPF es un protocolo dinámico de tipo link-state.  
- Usa el algoritmo SPF para calcular la mejor ruta.  
- Se organiza en áreas, con el área 0 como backbone.  
- DR y BDR reducen el tráfico en redes multiacceso.  

---

## 7. Recursos adicionales
- Cisco Official Guide: [OSPF Configuration](https://www.cisco.com/c/en/us/support/docs/ip/open-shortest-path-first-ospf/13684-12.html)  
- Simuladores: Cisco Packet Tracer, GNS3, EVE-NG  
- Comando útil: `show ip ospf neighbor` para verificar adyacencias
