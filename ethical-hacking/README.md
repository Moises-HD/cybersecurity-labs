# Hacking Ético — Máster Profesional de FP en Ciberseguridad

Este módulo se centra en la identificación, explotación y mitigación de vulnerabilidades en sistemas informáticos mediante metodologías de penetration testing profesionales.
Incluye prácticas de auditoría, pentesting en redes cableadas e inalámbricas, explotación de vulnerabilidades y análisis de aplicaciones web vulnerables.


## Resumen de prácticas

### 🧩 Planificación y ejecución de auditorías de seguridad

Se diseñó un plan de auditoría de ciberseguridad basado en escenarios reales:

- Pruebas externas: 
    Simulando ataques desde Internet (caja negra).

- Pruebas internas: 
    Evaluando amenazas desde dentro de la red corporativa (caja gris).

- Simulacros Red Team: 
    Combinando reconocimiento, explotación y movimiento lateral.

Se establecieron fases de auditoría (requisitos, pruebas, reporting, cierre) y se evaluaron vulnerabilidades reales usando métricas CVSS.

Entre las vulnerabilidades analizadas destacan:
- Falla de ejecución remota en servidor de correo.
- Inyección SQL en aplicaciones web.
- Ejecución de código en servidor FTP interno.

Cada vulnerabilidad se valoró en términos de impacto, explotabilidad y mitigación.


### 📡 Seguridad en redes Wi-Fi corporativas

Se auditaron tres configuraciones de red Wi-Fi (OPEN, WPA2-PSK y WPA2-Enterprise), identificando riesgos y mejoras:
- Red OPEN: 
    Sin cifrado ni control de acceso → riesgo de interceptación y suplantación.

- WPA2-PSK: 
    Una única clave compartida → falta de trazabilidad y control de dispositivos.

- WPA2-Enterprise: 
    Mejora la autenticación, pero requiere políticas MDM y segmentación.

Se propusieron contramedidas:
- Migrar a WPA3-Enterprise.
- Implementar MDM, segmentación por VLAN y validación estricta de certificados.
- Monitorización activa y rotación de credenciales.


### 💻 Fases de pentesting con Metasploit

Se construyó un laboratorio con Kali Linux y Metasploitable 2 para realizar un pentest completo:
- Reconocimiento: 
    Búsquedas dorking avanzadas (Google Hacking).

- Escaneo: 
    Detección de puertos y servicios con nmap -sV.

- Identificación de vulnerabilidades: 
    Con scripts vulscan.

- Explotación: 
    Uso del módulo vsftpd_234_backdoor en Metasploit, obteniendo acceso remoto al sistema.

- Resultado: 
    Comprensión práctica del flujo de un ataque controlado, desde el descubrimiento hasta la postexplotación.


### 🧠 Cracking y persistencia en entornos Windows

Se configuró un entorno de laboratorio con Windows 7 y Kali Linux para analizar técnicas ofensivas:
- Cracking de contraseñas con Hashcat, utilizando diferentes algoritmos:
    MD5 (-m 0)
    NTLM (-m 1000)
    NETNTLMv2 (-m 5600)
    Kerberos TGS (-m 13100)

- Explotación de la vulnerabilidad EternalBlue (MS17-010) mediante Metasploit, logrando acceso remoto.

- Persistencia postexplotación: 
    Mediante creación de servicios y claves de registro en Windows (sc create y reg add).

Estas prácticas simulan ataques avanzados de tipo Red Team en entornos Windows.


### 🌐 Vulnerabilidades web y pruebas con Burp Suite

Se utilizaron Burp Suite, DVWA y SQLMap para realizar auditorías de seguridad web:
- Ataque por fuerza bruta: 
    Contra formularios de login con Burp Intruder.

- Cross-Site Scripting (XSS) almacenado: 
    Ejecución de scripts en el navegador del usuario.

- Ejecución remota de comandos (RCE): 
    Mediante inyección en parámetros.

- Inyección SQL: 
    Manipulación de consultas SQL y extracción de bases de datos con sqlmap.

El objetivo fue comprender el impacto de las vulnerabilidades OWASP Top 10 y las mejores prácticas para mitigarlas.


## 🧰 Herramientas y tecnologías utilizadas

| Categoría | Herramientas / Tecnologías |
|------------|----------------------------|
| **Pentesting y explotación** | Metasploit, Nmap, Vulscan, Netcat |
| **Cracking y autenticación** | Hashcat, RockYou, John the Ripper |
| **Auditoría web** | Burp Suite, DVWA, SQLMap |
| **Redes inalámbricas** | WPA2/WPA3, RADIUS, Wireshark |
| **Sistemas operativos** | Kali Linux, Windows 7, Metasploitable 2 |
| **Metodologías** | OWASP, CVSS, Red Team / Blue Team |


---
Estas prácticas reflejan la aplicación controlada de técnicas ofensivas y defensivas, con el objetivo de fortalecer la seguridad de sistemas, redes y aplicaciones en entornos profesionales.