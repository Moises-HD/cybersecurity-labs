# Análisis Forense — Máster Profesional de FP en Ciberseguridad

Colección de prácticas realizadas en la asignatura Análisis Forense del Máster Profesional en Ciberseguridad.
Incluye ejercicios prácticos sobre captura y análisis de memoria, extracción de evidencias móviles, análisis forense en la nube, ingeniería inversa de firmware IoT y elaboración de informes periciales.


## Resumen general

Estas prácticas muestran la aplicación de metodologías forenses reales para la adquisición, preservación y análisis de evidencias digitales. El objetivo es combinar técnicas y criterios legales (cadena de custodia, clasificación TLP) para producir resultados replicables y válidos en contextos investigativos.


## Resumen de prácticas

### 🔍 Análisis de memoria RAM (server)

- Objetivo: 
    Analizar una imagen de memoria volátil para identificar actividad maliciosa y acciones del atacante.

- Herramientas: 
    Volatility (v2), FTK Imager.

- Técnicas clave: 
    imageinfo, pslist, cmdscan, netscan, malfind.

- Resultados destacados:
    Identificación de comandos utilizados por el atacante (creación de usuarios, habilitación de RDP).

    Detección de código inyectado y patrones compatibles con malware residente en memoria (fileless).

- Valor: 
    Capacidad para extraer indicadores de compromiso (IPs, procesos, comandos) desde RAM antes de apagados.


### 📱 Extracción y análisis de backups iOS

- Objetivo: 
    Obtener y procesar copia de seguridad lógica de un iPhone para extraer artefactos forenses.

- Herramientas: 
    iTunes, Magnet Acquire, iLEAPP, iBackup Viewer.

- Técnicas clave: 
    Extracción lógica (backup), procesamiento con iLEAPP, inspección de permisos y artefactos (contactos, apps).

- Resultados destacados:
    Generación de informe estructurado desde el backup.

    Identificación de riesgo de alteración por procesos del sistema (consideraciones de integridad).

- Valor: 
    Dominio de flujos de trabajo para extraer evidencias en dispositivos móviles cuando el acceso físico total no es posible.


### ☁️ Consideraciones forenses en entornos Cloud

- Objetivo: 
    Evaluar retos y garantías necesarias para realizar investigaciones forenses en servicios en la nube.

- Conceptos clave: 
    Soberanía de datos, acceso a logs, responsabilidad compartida (SLA), cumplimiento RGPD, derecho de portabilidad (art.20).

- Resultados destacados:
    Lista de requisitos mínimos que debe ofrecer un proveedor cloud para permitir un análisis forense adecuado: logs detallados, copias accesibles, auditorías y cláusulas contractuales.

- Valor: 
    Comprensión de las limitaciones prácticas y legales del análisis forense cloud.


### 💡 Análisis forense de firmware IoT

- Objetivo: 
    Extraer y analizar firmware de dispositivos IoT (bombilla, cámara) para identificar servicios, usuarios y vulnerabilidades de configuración.

- Herramientas: 
    binwalk, unsquashfs, Jefferson, grep.

- Técnicas clave: 
    Identificación de sistemas de ficheros (SquashFS, JFFS2), extracción de /etc, revisión de mosquitto.conf, búsqueda de usuarios en /etc/passwd.

- Resultados destacados:
    Detección de comunicación MQTT sin autenticación (allow_anonymous true) — riesgo crítico.

    Identificación de servicios embebidos (BusyBox, servidor web, DHCP) y usuarios (www-data, mosquitto).

    Kernel Linux embebido (ARM) y configuración de arranque (boot.sh) que facilitan trazabilidad.

- Valor: 
    Evidencia práctica de cómo el firmware revela la configuración y vectores de ataque en dispositivos IoT.


### 🧾 Informe pericial y cadena de custodia

- Objetivo: 
    Evaluar y redactar observaciones sobre un informe pericial (autenticidad, claridad, TLP y prácticas de custodia).

- Conceptos clave: 
    Cadena de custodia, Traffic Light Protocol (TLP), separación entre hechos probados e hipótesis, legibilidad del resumen ejecutivo.

- Resultados destacados: 
    Recomendaciones para mejorar reproducibilidad, inclusión de hashes y tabla de evidencias, y etiquetado TLP (p. ej. TLP:AMBER).

- Valor: 
    Habilidad para traducir hallazgos técnicos en conclusiones periciales con rigor legal y comunicativo.


## 🧰 Herramientas y tecnologías destacadas

| Categoría | Herramientas / Conceptos |
|------------|--------------------------|
| **Memoria volátil** | Volatility, FTK Imager |
| **Dispositivos iOS** | iLEAPP, iBackup Viewer, Magnet Acquire |
| **Firmware IoT** | Binwalk, unsquashfs, Jefferson |
| **Procesamiento auxiliar** | jq, grep, scripts Python |
| **Metodología y conceptos** | TLP, Cadena de custodia, RGPD, análisis de logs |


---
Estas prácticas reflejan la aplicación real de técnicas forenses en distintos entornos, priorizando la integridad de las evidencias, la trazabilidad del proceso y el cumplimiento normativo.