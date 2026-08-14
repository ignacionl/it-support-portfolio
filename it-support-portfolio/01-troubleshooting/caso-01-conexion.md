# 🛠️ Caso de Estudio #01: Pérdida de Conexión a Internet en Estación de Trabajo

## 📋 Información del Ticket
* **ID del Ticket:** INC-2026-001
* **Dispositivo:** PC de Escritorio (Windows 11)
* **Usuario:** Departamento de Administración
* **Nivel de Urgencia:** Medio
* **Estado:** Resuelto

---

## 🔍 1. Descripción del Problema
El usuario reporta que no puede acceder a internet ni a los recursos compartidos de la red de la oficina. Aparece un icono de "Sin acceso a internet" (globo terráqueo con indicador de alerta) en la barra de tareas.

---

## 🔎 2. Proceso de Diagnóstico (Metodología de Google)

Siguiendo los pasos lógicos de aislamiento de problemas (de la capa física a la lógica):

1. **Verificación Física (Capa 1):**
   * Se revisa el cable Ethernet (RJ45). Estaba correctamente conectado al puerto de la PC y al switch de la oficina, y las luces LED del puerto parpadeaban, descartando un daño físico grave del cable o puerto.

2. **Verificación de Red Local (Capa 2 y 3 - IP):**
   * Se abrió la terminal (`cmd`) y se ejecutó `ipconfig`.
   * **Resultado:** La dirección IP asignada era del rango `169.254.x.x` (IP APIPA). Esto indica que la computadora no pudo comunicarse con un servidor DHCP para obtener una dirección IP válida.

3. **Prueba de Conectividad:**
   * Se intentó hacer ping a la puerta de enlace predeterminada (`ping 192.168.1.1`) y el resultado fue *Tiempo de espera agotado (Request timed out)*.

---

## 💡 3. Solución Aplicada

Para resolver el problema de la asignación de IP y restablecer la pila de red, se ejecutaron los siguientes comandos en la terminal de Windows (como Administrador):

```cmd
# 1. Liberar y renovar la dirección IP
ipconfig /release
ipconfig /renew

# 2. Limpiar la caché del DNS
ipconfig /flushdns

# 3. Reiniciar el catálogo Winsock y la pila IP
netsh winsock reset
netsh int ip reset