# Tema 3: Gestión de Estructuras de Almacenamiento

El almacenamiento es uno de los pilares de cualquier sistema. En este tema veremos cómo organizar el espacio en disco.

## 1. Particionado de Discos
Antes de usar un disco, debemos dividirlo en secciones lógicas llamadas particiones.

- **MBR (Master Boot Record)**: Estándar antiguo, máximo 4 particiones primarias y discos de hasta 2TB.
- **GPT (GUID Partition Table)**: Estándar moderno, permite cientos de particiones y discos de enorme tamaño.

## 2. Sistemas de Archivos
Es el "idioma" en el que el SO escribe los datos.
- **NTFS**: El estándar de Windows. Soporta permisos y compresión.
- **EXT4**: El estándar más común en Linux. Muy eficiente y robusto.
- **FAT32/exFAT**: Para compatibilidad entre diferentes sistemas.

## 3. Práctica en Linux: Añadir un segundo disco
Imagina que añadimos un disco nuevo de 10GB a nuestra VM. Los pasos serían:

```bash
# 1. Identificar el nuevo disco (normalmente /dev/sdb)
lsblk

# 2. Crear una nueva partición (usando fdisk)
# sudo fdisk /dev/sdb

# 3. Formatear la partición con EXT4
sudo mkfs.ext4 /dev/sdb1

# 4. Montar el disco en una carpeta
sudo mkdir /mnt/datos
sudo mount /dev/sdb1 /mnt/datos
```

> **¿Por qué formatear y montar?**
> Un disco sin formatear es como un libro con páginas en blanco sin líneas. `mkfs.ext4` dibuja las "líneas" (la estructura de datos). `mount` le dice al sistema operativo en qué carpeta queremos ver el contenido de ese disco físico.

## 4. Cuotas de Disco
En entornos multiusuario, es vital limitar cuánto espacio puede usar cada persona para evitar que un solo usuario llene todo el disco del servidor.
