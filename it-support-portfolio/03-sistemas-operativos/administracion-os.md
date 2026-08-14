# 🖥️ Administración de Sistemas Operativos: Notas Técnicas

Este documento resume procedimientos críticos de administración de sistemas en Windows y Linux, fundamentales para tareas de soporte de Nivel 1 y Nivel 2.

---

## 🐧 Linux (Debian/Ubuntu)

La gestión de usuarios y permisos es el corazón de la seguridad en Linux.

### Gestión de Usuarios
* **Crear usuario:** `sudo adduser nombre_usuario`
* **Cambiar contraseña:** `sudo passwd nombre_usuario`
* **Eliminar usuario:** `sudo deluser nombre_usuario`

### Gestión de Permisos (La regla de oro)
En Linux, los permisos se dividen en **Lectura (r), Escritura (w) y Ejecución (x)** para el **Propietario, Grupo y Otros**.

* **Ejemplo:** `chmod 755 archivo.txt`
  * `7` (rwx) para el dueño.
  * `5` (r-x) para el grupo.
  * `5` (r-x) para otros.
* **Cambiar dueño:** `sudo chown usuario:grupo archivo.txt`

---

## 🪟 Windows (PowerShell)

Automatizar tareas en Windows mediante la terminal ahorra tiempo valioso.

### Gestión de Usuarios y Grupos
* **Listar usuarios:** `Get-LocalUser`
* **Crear usuario:** `New-LocalUser -Name "Nombre" -Description "Usuario de prueba"`
* **Añadir a grupo administrador:** `Add-LocalGroupMember -Group "Administradores" -Member "Nombre"`

### Gestión de Servicios (Troubleshooting)
Cuando una aplicación falla, el primer paso es verificar si el servicio está corriendo:
* **Listar servicios:** `Get-Service`
* **Reiniciar servicio:** `Restart-Service -Name "NombreServicio"`

---

## 🚀 Virtualización: Tu Laboratorio Personal

Para practicar estos comandos sin riesgo para tu equipo real, recomiendo el uso de máquinas virtuales:
1. **Software recomendado:** VirtualBox o VMware Workstation Player.
2. **Escenario de práctica:** Crea una MV con Ubuntu Server y otra con Windows 10/11.
3. **Tarea:** Intenta crear un usuario en ambas máquinas y asignarle privilegios de lectura/escritura en una carpeta específica.

---
*Nota: Siempre ejecuta comandos que modifiquen el sistema con precaución y, preferiblemente, dentro de un entorno virtualizado.*