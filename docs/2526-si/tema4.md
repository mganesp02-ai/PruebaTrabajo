# Tema 4: Administración de Usuarios y Seguridad

Un sistema informático solo es útil si es seguro y permite la colaboración organizada de varios usuarios.

## 1. Gestión de Usuarios y Grupos
Los sistemas operativos modernos son multiusuario. Para organizar los accesos, utilizamos:
- **Usuarios**: Cuentas individuales.
- **Grupos**: Conjuntos de usuarios que comparten los mismos privilegios.

### Comandos de gestión en Linux:
```bash
# Crear un nuevo grupo llamado 'desarrolladores'
sudo groupadd desarrolladores

# Crear un usuario y añadirlo al grupo
sudo useradd -m -g desarrolladores marta

# Cambiar la contraseña del usuario
sudo passwd marta
```

> **¿Por qué usar grupos?**
> Es mucho más eficiente gestionar permisos para un grupo (ej. "contabilidad") que ir usuario por usuario. Si entra alguien nuevo, simplemente lo añades al grupo y hereda todos los permisos necesarios automáticamente.

## 2. Permisos de Archivos (Linux vs Windows)

### En Linux:
Utilizamos el sistema UGO (User, Group, Others) y el comando `chmod`.
- **r (read)**: 4
- **w (write)**: 2
- **x (execute)**: 1

```bash
# Dar permisos de lectura y escritura al dueño, y lectura al resto
chmod 644 documento.txt
```

### En Windows:
Se utilizan las **ACL (Listas de Control de Acceso)**, que son mucho más granulares y se gestionan habitualmente desde la pestaña "Seguridad" de las propiedades del archivo o mediante el comando `icacls`.

## 3. Seguridad Básica y Auditoría
- **Principio de menor privilegio**: Un usuario solo debe tener los permisos mínimos necesarios para hacer su trabajo.
- **Auditoría**: Revisar los "Logs" o registros del sistema para saber quién ha accedido a qué y cuándo.
