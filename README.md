# Análisis de Honeypots con Cowrie

🛡 **Simulación de un servidor SSH/Telnet vulnerable para el estudio de ataques y comportamiento de atacantes**  

Este repositorio contiene el informe del **Laboratorio de Honeypots**, donde se ha desplegado **Cowrie**, un honeypot diseñado para registrar intentos de acceso no autorizado, capturar comandos ejecutados por atacantes y analizar archivos maliciosos descargados.

## 🔍 Descripción

El objetivo de esta práctica es implementar y configurar **Cowrie**, un honeypot avanzado que simula un servidor SSH y Telnet vulnerable, para recopilar información sobre:
- **Intentos de autenticación maliciosos** con credenciales comunes.
- **Ejecución de comandos en un entorno simulado** para estudiar el comportamiento de los atacantes.
- **Descarga de archivos maliciosos** para su análisis posterior.
- **Escaneos de red y reconocimiento de puertos** realizados por actores externos.

## 📁 Contenido del Repositorio

- `HONEYPOT_Enrique_García_Cuadrado.pdf` → Informe completo con configuración, pruebas y análisis de logs.
- **Configuraciones personalizadas de Cowrie y scripts de automatización** (próximamente).

## 🛠 Herramientas Utilizadas

### 🔹 **Configuración y Despliegue de Cowrie**
- **Entorno virtual en Python** (`venv`) para ejecución aislada.
- **Modificación de hostname y parámetros** para hacer el honeypot más realista.
- **Activación de Telnet** para atraer más intentos de ataque.
- **Configuración de logs en JSON** para facilitar la integración con herramientas externas como:
  - **Elasticsearch** (para análisis avanzado de logs).
  - **VirusTotal** (para escaneo automático de archivos maliciosos).
  - **Splunk, MongoDB, Telegram y Discord** (para notificaciones y almacenamiento de eventos).

### 🔹 **Pruebas Realizadas**
1. **Intentos de acceso SSH**:
   - Registro de credenciales utilizadas en ataques de fuerza bruta.
   - Análisis de patrones de intentos de conexión desde direcciones IP externas.

2. **Ataque de fuerza bruta con Hydra**:
   - Uso del diccionario `rockyou.txt` para probar credenciales comunes.
   - Registro de intentos fallidos y detección de contraseñas exitosas.

3. **Ejecución de comandos en la sesión SSH**:
   - Captura de comandos utilizados por el atacante tras obtener acceso.
   - Registro detallado en logs de Cowrie.

4. **Descarga de archivos maliciosos**:
   - Identificación de malware subido por atacantes a la sesión de Cowrie.
   - Almacenamiento automático de archivos en una carpeta para análisis con Ghidra o sandbox.

5. **Escaneo de puertos con Nmap**:
   - Detección de intentos de reconocimiento de red.
   - Registro del atacante y puertos analizados.

6. **Intento de conexión Telnet**:
   - Registro de accesos y comandos ejecutados en el servicio Telnet simulado.

## 🚀 Resultados y Hallazgos

| Prueba Realizada  | Hallazgo Principal |
|------------------|------------------|
| **Ataques SSH** | Credenciales más probadas: `root`, `admin`, `12345` |
| **Fuerza Bruta con Hydra** | 15 credenciales exitosas descubiertas en pocos minutos |
| **Ejecución de comandos** | Detección de reconocimiento del sistema tras acceso |
| **Descarga de malware** | Honeypot almacenó archivos para análisis posterior |
| **Escaneo de red con Nmap** | Registro de IP atacante y puertos analizados |
| **Conexión Telnet** | Simulación de acceso remoto y registro de comandos |

## 📌 Posibles Mejoras

- **Integración con ELK Stack (Elasticsearch, Logstash, Kibana)** para visualizar los ataques en tiempo real.
- **Automatización del análisis de malware** descargado con herramientas de sandboxing.
- **Despliegue del honeypot en una red expuesta** para recolectar más intentos de ataque reales.
- **Notificaciones en tiempo real vía Telegram o Discord** cuando se detecten conexiones sospechosas.

## 🎥 Demostración en Vivo

📽️ Enlace al video de demostración de la práctica:  
🔗 [Ver en Vimeo](https://vimeo.com/1045773275?share=copy)

## 🤝 Contribuciones

Si deseas mejorar este análisis, agregar más funcionalidades al honeypot o compartir nuevas pruebas de seguridad, haz un **fork**, añade tus cambios y envía un **Pull Request**.

## 📜 Licencia

Este proyecto se distribuye bajo la licencia **MIT**. Consulta el archivo `LICENSE` para más detalles.
