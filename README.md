# Informe técnico de Seguridad en Redes Corporativas

Este repositorio contiene el archivo de simulación en **Cisco Packet Tracer** y el informe técnico asociado al proyecto **Prueba Módulo 5 – Seguridad en redes corporativas**.  
El objetivo fue diseñar, implementar y documentar medidas de seguridad y configuración avanzada en una red corporativa.

---

## 📂 Contenido del repositorio

- `Prueba modulo 5.pdf` → Informe técnico con la descripción detallada de la implementación.  
- `Prueba modulo 5.pkt` → Archivo de simulación en Packet Tracer.  

---

## 🛠️ Requerimientos implementados

### 1. Direccionamiento IP, contraseñas seguras y VLANs
- Asignación de **IPv4/IPv6** en routers y dispositivos finales.  
- **DHCP** configurado en la VLAN 20 (solo para IPv4).  
- Fortalecimiento de accesos:
  - `enable secret` en modo privilegiado.  
  - Contraseñas en consola (`line console 0`) y remoto (`line vty`).  
  - Banner de advertencia para accesos no autorizados.  
- Creación de **VLANs** y asignación de interfaces según topología.  

### 2. Enlaces troncales, STP y estabilidad
- Configuración de **enlaces troncales** limitados a VLANs de datos.  
- Cambio de **VLAN nativa** (de 1 a VLAN 10).  
- Deshabilitación de **DTP** en enlaces troncales.  
- Implementación de **Rapid PVST+** con SWD como *root bridge*.  
- **PortFast** y **BPDU Guard** en puertos de acceso.  

### 3. Seguridad de capa 2 y DHCP Snooping
- Seguridad de puertos:
  - SWA → dinámica.  
  - SWB → máxima de 2 MAC, con *shutdown* al exceder.  
- Control de tormentas al **20%** en enlaces troncales.  
- **DHCP Snooping** en VLAN 20, permitiendo solo 2 IP por minuto y validando contra DHCP legítimo.  

### 4. Enrutamiento, Syslog y control de acceso
- **Inter-VLAN Routing** (IPv4 e IPv6) en el switch CORE.  
- Rutas por defecto en IPv6 hacia la red externa.  
- Configuración de **Syslog**: switches reportando al servidor central.  
- **ACLs**: restricción de comunicación entre VLAN 10 y VLAN 20 (IPv4/IPv6).  
- Integración de **TACACS+** en el router BORDE para autenticación centralizada.  

---

## 📸 Evidencias
El informe incluye capturas de:
- `show ip interface brief` y `show ipv6 interface brief`.  
- Asignación de IPs por DHCP.  
- Seguridad en puertos y troncales.  
- Pruebas de conectividad antes y después de aplicar ACLs.  
- Acceso autenticado mediante TACACS+.  

---

## 🚀 Uso del archivo `.pkt`
1. Abrir el archivo `Prueba modulo 5.pkt` en **Cisco Packet Tracer (v8.x o superior)**.  
2. Verificar las configuraciones en routers y switches.  
3. Probar la conectividad entre VLANs y hacia la red externa.  
4. Revisar el comportamiento de seguridad (DHCP Snooping, ACLs, STP, etc.).  

---

## 👤 Autor
- **Daniel Dávila**  

---
