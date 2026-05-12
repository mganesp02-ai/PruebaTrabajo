# Tema 5: Automatización de Tareas (Scripting)

Como futuros desarrolladores, automatizar tareas repetitivas es una habilidad esencial. En este tema aprenderemos las bases de Bash (Linux) y PowerShell (Windows).

## 1. Introducción al Scripting
Un script es un archivo de texto que contiene una secuencia de comandos que el sistema ejecuta de forma automática.

## 2. Bash Scripting (Linux)
Todos los scripts de Bash deben empezar con el "shebang": `#!/bin/bash`.

### Ejemplo: Script de copia de seguridad
Este script crea una carpeta y copia un archivo dentro, añadiendo la fecha al nombre.

```bash
#!/bin/bash

# Definimos variables
FECHA=$(date +%Y-%m-%d)
DESTINO="/home/usuario/backups"

# Creamos el directorio si no existe
mkdir -p $DESTINO

# Copiamos el archivo (explicación: -v para ver qué ocurre)
cp -v datos.txt $DESTINO/datos_$FECHA.txt

echo "Copia de seguridad completada el $FECHA"
```

> **¿Por qué usamos variables y shebang?**
> El shebang `#!/bin/bash` le indica al kernel qué intérprete debe usar para leer el archivo. Las variables como `$FECHA` hacen que el script sea reutilizable y fácil de mantener.

## 3. PowerShell (Windows)
PowerShell es más que una consola; es un entorno basado en objetos y .NET.

### Ejemplo: Listar procesos que consumen mucha memoria
```powershell
# Obtiene los 5 procesos que más RAM consumen
Get-Process | Sort-Object WorkingSet64 -Descending | Select-Object -First 5
```

## 4. Estructuras de Control
Para que un script tome decisiones, usamos:
- **IF/ELSE**: "Si pasa esto, haz aquello".
- **FOR/WHILE**: "Repite esto 10 veces" o "mientras el servidor esté caído".
