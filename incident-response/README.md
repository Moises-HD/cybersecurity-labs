# Incidentes de Ciberseguridad — Máster Profesional de FP en Ciberseguridad

Este módulo se centra en la gestión integral de incidentes de ciberseguridad, desde la identificación y clasificación de activos hasta la respuesta técnica, comunicación con equipos CSIRT y monitorización mediante SIEM.
Incluye prácticas con entornos simulados de detección, análisis y mitigación de ataques reales.


## Resumen de prácticas

### 🧩 Identificación y auditoría de activos críticos

Se diseñó la arquitectura de red de una empresa ficticia con entornos segmentados (LAN, DMZ y Smart Factory).
Se inventariaron los activos clave —como servidores SOC, ERP, NAS, PLC y SCADA—, evaluando su criticidad, dependencias y requisitos de seguridad.

Para cada activo se definieron:
- Controles antimalware, permisos, cumplimiento normativo y monitorización.
- Auditorías aplicables: hacking ético, seguridad perimetral, revisión forense y legal.
- Estrategias de mejora continua mediante modelos CMMI y el ciclo PDCA, priorizando la optimización constante y la respuesta ágil ante incidentes.


### ⚙️ Priorización de riesgos y taxonomía de incidentes

Se estableció una jerarquía de activos por capas (comunicación, servicio, equipamiento e información) para evaluar amenazas y salvaguardas.
Se aplicaron metodologías de valoración de riesgo y taxonomía de incidentes:
- SOC: 
    Intrusión y compromiso de seguridad lógica.

- ERP: 
    Ataques DoS que afectan la disponibilidad.

- Base de datos de inventario: 
    Compromiso de integridad mediante inyección SQL.

- Router: 
    Interrupciones por fallos de configuración o ataques remotos.

El resultado fue una matriz de riesgo y gráficos de criticidad, que permiten priorizar los activos y las respuestas ante ataques.


### 🕵️ Análisis de un incidente de phishing y persistencia

Se simuló un incidente de ingeniería social (phishing) en el que un empleado descargaba un ejecutable malicioso (“Putty.exe”).
Mediante análisis forense se detectaron:
- Conexiones activas no autorizadas (puerto 139 / SMB).
- Ejecución de procesos sospechosos (nc.exe) vinculados a Netcat como puerta trasera.
- Entradas persistentes en el registro de Windows (HKCU\Software\Microsoft\Windows\CurrentVersion\Run).
- Errores en el visor de eventos que evidenciaban intentos de ejecución automática.

Se verificó la integridad de la imagen del disco con QuickHash, detectando archivos corrompidos y alteraciones en cabeceras, demostrando la manipulación de evidencias.


### 🧠 Gestión y respuesta ante incidentes

Se documentaron los procesos de detección, análisis, contención, mitigación y recuperación:
- Monitorización proactiva con IDS/SIEM y revisión de logs en tiempo real.
- Clasificación de incidentes según criticidad (bajo, medio, alto).
- Roles definidos en el CSIRT corporativo: CISO, SOC, TI, Legal, CEO/CSO.
- Planes de formación, simulacros y comunicación interna.

Se elaboró un playbook de respuesta ante ransomware, incluyendo:
- Aislamiento de sistemas comprometidos.
- No pago del rescate.
- Restauración desde copias verificadas.
- Refuerzo de configuraciones y concienciación de empleados.


### 🧾 Notificación y coordinación con CSIRT

Se redactó un informe realista de incidente web con inyección de código malicioso (Web Attack):
- Clasificación oficial: 
    Ataque Web – Inyección de Código Malicioso.

- Nivel de peligrosidad: 
    Crítico.

- Impacto: 
    Muy Alto, con riesgo de exfiltración y manipulación de datos.

- Obligación de notificación: 
    CCN-CERT (CSIRT nacional).

Incluyó todos los campos de notificación exigidos (fecha, impacto, medidas, daños reputacionales y regulación afectada: ENS, RGPD), junto con fases de comunicación: aviso inicial, seguimiento y cierre.


### 🧩 Implementación de un IDS con Snort

Se configuró un entorno con Ubuntu Server, SOC, IDS (Snort) y WebServer en DMZ:
- Configuración de red interna (192.168.2.0/24) y externa (192.168.1.0/24).
- Instalación y ajuste de Snort (/etc/snort/snort.conf).
- Creación de reglas personalizadas para:
    Pings internos y externos.
    Conexiones SSH y HTTP.
    Accesos no autorizados a /phpmyadmin.

- Verificación de logs (/var/log/snort/alert) y validación con pruebas reales de tráfico.


### 📊 Monitorización con ELK Stack

Se implementó una pila SIEM con Elastic Stack (Elasticsearch, Logstash, Kibana, Filebeat):
- Elasticsearch: 
    Almacenamiento y consulta de logs.

- Kibana: 
    Panel de control web para visualización.

- Filebeat: 
    Envío de registros de Snort al servidor de Logstash.

- Logstash: 
    Filtrado y creación de pipelines personalizados.

Se diseñaron dashboards con:
- Contadores de PINGs internos y externos.
- Histogramas de intentos de conexión SSH y accesos a phpMyAdmin.


## 🧰 Herramientas y tecnologías utilizadas

| Categoría | Herramientas / Tecnologías |
|------------|----------------------------|
| **Análisis y detección** | Snort, IDS/IPS, Nmap, Wireshark |
| **Gestión y monitorización** | ELK Stack (Elastic, Logstash, Kibana, Filebeat) |
| **Gestión de incidentes** | SIEM, SOC, QuickHash, Visor de eventos |
| **Respuesta y mitigación** | Modelos PDCA y CMMI, CSIRT, CCN-CERT |
| **Sistemas y redes** | Ubuntu Server, Windows, DMZ, VLAN |
| **Metodologías** | Taxonomía de incidentes, Gestión de riesgos, ENS, RGPD |


---
Estas prácticas muestran la aplicación completa del ciclo de vida de gestión de incidentes, desde la detección inicial hasta la mitigación y la comunicación con equipos CSIRT, reforzando las capacidades de respuesta ante ciberataques reales.