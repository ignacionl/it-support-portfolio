# 🛡️ Ciberseguridad: Guía de Buenas Prácticas para Soporte TI

Esta guía recopila los principios fundamentales de seguridad de la información y ciberseguridad que todo técnico de soporte debe aplicar y promover entre los usuarios de la organización.

---

## 🔑 1. Gestión de Identidades y Accesos (IAM)

El robo de credenciales es el vector de ataque número uno.

* **Autenticación Multifactor (MFA):** Obligatoria para todos los accesos corporativos (correo, VPN, sistemas internos). Una contraseña ya no es suficiente.
* **Principio de Menor Privilegio (PoLP):** Los usuarios y las cuentas de servicio solo deben tener los permisos estrictamente necesarios para realizar sus tareas diarias. Nadie debe ser Administrador por defecto en su equipo de trabajo.
* **Políticas de Contraseñas:** Fomentar el uso de frases de contraseña (*passphrases* de más de 12 caracteres) en lugar de contraseñas complejas pero cortas y fáciles de olvidar (ej: `GatoAzul2026!`).

---

## 🎣 2. Identificación y Mitigación de Phishing

Los usuarios suelen acudir a soporte cuando sospechan de un correo. Debes saber identificar las señales de alerta:

* **Señales de alarma comunes:**
  * Urgencia injustificada ("¡Su cuenta será suspendida en 2 horas si no hace clic aquí!").
  * Remitentes sospechosos (dominios ligeramente alterados, ej: `soporte@micros0ft.com` en lugar de `microsoft.com`).
  * Enlaces acortados o discrepancias entre el texto del enlace y la URL real de destino.
* **Protocolo de actuación ante un ataque:**
  1. Aislar el equipo del usuario de la red si se hizo clic en un enlace malicioso o se ejecutó un archivo adjunto.
  2. Notificar inmediatamente al equipo de Seguridad de la Información (SOC).
  3. Cambiar contraseñas de inmediato desde un dispositivo seguro.

---

## 💻 3. Endpoints y Dispositivos Seguros

Proteger las estaciones de trabajo físicas y virtuales:

* **Actualizaciones y Parches:** El software desactualizado es la vía de entrada para el *ransomware*. Mantener el sistema operativo y los navegadores siempre al día.
* **Cifrado de Discos (BitLocker / LUKS):** Todo ordenador portátil o de escritorio de la empresa debe tener el disco duro cifrado para evitar la fuga de datos en caso de robo o pérdida física.
* **Bloqueo de Sesión:** Enseñar a los usuarios el hábito de bloquear su equipo cada vez que se levanten de su escritorio (atajos: `Windows + L` en Windows, `Super + L` en Linux).

---

## 📝 4. Checklist Rápido para Soporte (Incidentes Comunes)

| Situación | Acción Inmediata de Soporte |
| :--- | :--- |
| **Usuario comparte su contraseña** | Forzar cambio inmediato de contraseña y revisar accesos recientes. |
| **Pérdida de un portátil corporativo** | Notificar a seguridad para bloqueo remoto y activar borrado si es necesario. |
| **Alerta de Antivirus / EDR** | Aislar la máquina de la red y analizar el reporte del endpoint. |

---
*La seguridad es un proceso, no un producto. La concienciación del usuario final es nuestra mejor barrera.*