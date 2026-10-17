# Reporte de Pruebas - Red Team (Avance 2)

## 1. Información General
- **Objetivo:** Evaluación de seguridad ofensiva en entorno controlado de Microsoft Azure[cite: 1].
- **Herramientas empleadas:** Python 3.x, Nmap, Scapy, Paramiko[cite: 1].

## 2. Escaneo de Puertos y Servicios (`scanner.py`)
- **Metodología:** Se ejecutó un escaneo SYN sigiloso y de detección de versiones sobre la máquina virtual del Blue Team[cite: 1].
- **Evidencias y Hallazgos:**
  - Se identificaron los puertos abiertos principales (ej. Puerto 22 SSH, Puerto 80 HTTP).
  - Listado de servicios expuestos en la red.

## 3. Análisis de Tráfico y Spoofing (`packet_attack.py`)
- **Metodología:** Se utilizó Scapy desde la máquina virtual atacante conectada en la misma red local virtual para realizar pruebas de captura de paquetes y suplantación ARP[cite: 1].
- **Evidencias y Hallazgos:**
  - Demostración de vulnerabilidad ante interceptación de tráfico en redes locales no segmentadas.

## 4. Pruebas de Acceso No Autorizado (`ssh_brute.py`)
- **Metodología:** Se ejecutó un ataque de diccionario automatizado contra el servicio SSH utilizando credenciales comunes[cite: 1].
- **Evidencias y Hallazgos:**
  - Comprobación de la robustez (o debilidad) de las contraseñas configuradas en las cuentas de usuario de la máquina objetivo.

## 5. Conclusiones y Recomendaciones de Endurecimiento (Hardening)
- Restringir el acceso mediante reglas estrictas en los **Network Security Groups (NSG)** de Azure.
- Deshabilitar la autenticación por contraseña en SSH y obligar el uso de llaves criptográficas (SSH Keys).
- Monitorear eventos inusuales mediante Azure Monitor[cite: 1].