# 🌐 Cheatsheet: Comandos de Diagnóstico de Red

Esta es una guía de referencia rápida para el diagnóstico de conectividad en Windows y Linux. Estos comandos son esenciales para el troubleshooting diario.

## 🖥️ Comandos en Windows (CMD / PowerShell)

| Comando | Descripción |
| :--- | :--- |
| `ipconfig` | Muestra la configuración IP actual (IP, Máscara, Gateway). |
| `ipconfig /all` | Muestra información detallada, incluyendo la dirección MAC (Física) y DNS. |
| `ping [destino]` | Verifica la conectividad básica enviando paquetes ICMP. |
| `tracert [destino]` | Muestra la ruta que siguen los paquetes hasta llegar al destino (útil para detectar dónde se pierde la señal). |
| `nslookup [dominio]` | Consulta al servidor DNS para verificar la resolución de nombres (ej. `nslookup google.com`). |
| `netstat -an` | Muestra todas las conexiones de red activas y los puertos abiertos en el equipo. |

---

## 🐧 Comandos en Linux (Terminal)

| Comando | Descripción |
| :--- | :--- |
| `ip a` (o `ifconfig`) | Muestra las interfaces de red y sus direcciones IP asociadas. |
| `ping -c 4 [destino]` | Envía 4 paquetes ICMP (en Linux el ping no termina solo, usa `-c`). |
| `traceroute [destino]` | Similar a `tracert`, muestra los saltos de red hasta el destino. |
| `dig [dominio]` | Herramienta potente para consultar servidores DNS. |
| `ss -tuln` | Muestra puertos abiertos y procesos escuchando en el sistema (el moderno `netstat`). |

---

## 🛠️ Pequeño Script de Diagnóstico (Bash)

Si alguna vez necesitas comprobar rápidamente si tienes conexión a internet desde un servidor Linux, puedes guardar este pequeño script como `check_net.sh`:

```bash
#!/bin/bash
# Script básico para verificar conectividad
TARGET="8.8.8.8"

if ping -c 1 $TARGET &> /dev/null
then
    echo "✅ Conectividad a internet OK"
else
    echo "❌ Error: Sin conexión a internet"
fi