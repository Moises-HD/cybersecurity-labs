# Bastionado de Redes y Sistemas — Máster Profesional de FP en Ciberseguridad

Este módulo se centra en la protección y endurecimiento de redes, servidores y sistemas operativos, aplicando metodologías de seguridad como el paradigma Zero Trust, la segmentación de redes, la autenticación multifactor y la configuración segura de servicios.


## Resumen de prácticas

### 🔐 Paradigma Zero Trust

Se analizó el modelo Zero Trust, que establece que ningún usuario o sistema debe considerarse confiable por defecto.
Se estudiaron soluciones de referencia como Zscaler Zero Trust Exchange y Fortinet ZTA, implementando políticas de acceso basadas en identidad, contexto y microsegmentación.

- Objetivo: 
    Minimizar la superficie de ataque y prevenir movimientos laterales en la red.


### 🧱 Auditoría y propuesta de bastionado de una empresa

Se evaluó el entorno TI de la empresa ficticia Venus SA, identificando debilidades como la falta de separación de entornos, ausencia de control de accesos y mala ubicación física de servidores.
Se propusieron medidas de mitigación:

Separar servicios en entornos seguros (web, gestión, copias).

Definir roles de usuario y mínimos privilegios.

Contratar personal cualificado y establecer políticas de seguridad y auditorías periódicas.


### 🔑 Autenticación 2FA y MFA

Se compararon los sistemas de autenticación de dos y múltiples factores, detallando sus ventajas y desventajas.

- Ejemplos prácticos:
    Gmail y Facebook con 2FA por SMS o app.

Banca online con MFA mediante token físico.

- Conclusión: 
    Estas soluciones reducen drásticamente accesos no autorizados, aunque aumentan la complejidad operativa.


### 📡 Implementación de servidor RADIUS

Se configuró un servidor FreeRADIUS en Ubuntu para autenticar clientes Wi-Fi mediante WPA2-Enterprise.
Se definieron clientes en clients.conf y se documentó la configuración de autenticación con hostapd.
Aunque el entorno no contaba con adaptador físico, se demostró el proceso completo de instalación, configuración y validación de servicio.


### 🧩 Filtrado MAC e IDS con Snort

Se realizó un ejercicio práctico de filtrado de direcciones MAC en router doméstico y manipulación de MAC en Ubuntu para simular accesos restringidos.
Posteriormente, se instaló Snort como IDS para monitorizar tráfico y detectar escaneos con Nmap desde Kali Linux.
Los registros (snort.alert.fast) permitieron identificar tráfico sospechoso y validar la eficacia de las reglas.


### 🕸️ Diseño de red segmentada con VLANs y DMZ

Se diseñó una arquitectura de red con segmentación en VLANs (10, 20, 30 y 40) para aislar servicios críticos, gestión, empleados y red pública.
Se implementó una DMZ con servidores web, DNS y VPN, protegida por dos firewalls (perimetral e interno).
Se definieron reglas precisas de acceso por IP, puerto y protocolo, junto a medidas de seguridad en servicios en la nube (TLS, 2FA, CASB y backups).


### ⚔️ Análisis de ataques DDoS y Web

Se analizaron logs de Apache, SSH y FTP para identificar intentos de ataque DDoS, fuerza bruta y exfiltración de datos.
La IP atacante interna 192.168.10.5 realizaba escaneos con Nmap y accesos anónimos FTP.

- Contramedidas: 
    Bloqueo temporal, monitorización en tiempo real y análisis de logs del firewall para trazabilidad del incidente.


### 🧮 Revisión de permisos y auditoría de seguridad en Linux

Se revisaron directorios y binarios con permisos inseguros (find / -perm) y posibles escaladas de privilegios mediante GTFOBins.

También se analizaron:
- Permisos en $PATH.
- Carpetas compartidas inseguras.
- Opciones de montaje en /etc/fstab.
- Uso de borrado seguro con shred.

- Objetivo: 
    Eliminar configuraciones que permitan ejecución o escritura no controlada.


### 🧰 Endurecimiento de SSH y controles de acceso remoto

Se implementaron configuraciones avanzadas de bastionado SSH:
- Bloqueo de acceso root remoto.
- Desconexión tras 5 minutos de inactividad.
- Autenticación por clave pública/privada.
- Limitación por usuarios e IPs.
- Desactivación de Port Forwarding y X11 Forwarding.
- Uso de protocolos seguros (SSH v2, SHA2-512/256).
- Registro detallado en /var/log/auth.log para envío al SOC.

- Resultado: 
    Conexión cifrada, autenticación reforzada y registro completo de actividad.


## 🧰 Herramientas y tecnologías utilizadas

| Categoría | Herramientas / Tecnologías |
|------------|----------------------------|
| **Redes y segmentación** | VLANs, DMZ, Firewalls, Proxy inverso |
| **Autenticación y control** | FreeRADIUS, WPA2-Enterprise, 2FA/MFA |
| **Monitorización y detección** | Snort, Nmap, UFW, IDS/IPS |
| **Análisis y auditoría** | GTFOBins, find, chmod, fstab, whois |
| **Protocolos y cifrado** | SSH, TLS, HTTPS, SHA2 |
| **Modelos de seguridad** | Zero Trust, Seguridad perimetral, Control de acceso mínimo |


---
Estas prácticas demuestran la aplicación de estrategias de bastionado de redes y sistemas en entornos reales, priorizando la seguridad por capas, la segmentación lógica y el principio de mínimo privilegio.