# Tema 2: Virtualización e Instalación de Sistemas Operativos

En este tema aprenderemos a preparar el entorno de trabajo mediante la virtualización y el despliegue de sistemas operativos.

## 1. ¿Qué es la Virtualización?
La virtualización nos permite ejecutar múltiples sistemas operativos (invitados) sobre un único hardware físico (anfitrión).

### Beneficios
- **Aislamiento**: Los fallos en una VM no afectan al anfitrión.
- **Pruebas**: Ideal para entornos de desarrollo y aprendizaje.
- **Portabilidad**: Podemos mover máquinas virtuales entre diferentes equipos.

## 2. Instalación de VirtualBox
VirtualBox es un hipervisor de tipo 2 muy popular en entornos educativos.

### Pasos de Instalación
1. Descargar el instalador de la web oficial.
2. Seguir el asistente (Next, Next, Install).
3. **Importante**: Habilitar la virtualización (VT-x o AMD-V) en la BIOS/UEFI de tu ordenador real.

## 3. Creación de una Máquina Virtual Linux (Ubuntu Server)
Para instalar Ubuntu en una VM, seguiremos estos pasos:

1. Seleccionar "Nueva" en VirtualBox.
2. Asignar al menos 2GB de RAM y 20GB de disco duro.
3. Cargar la ISO de Ubuntu.

### Configuración de Red inicial
```bash
# Comprobar la IP asignada por el servidor DHCP de VirtualBox
ip addr show
```

> **Explicación del comando**:
> `ip addr show` nos muestra el estado de todas las interfaces de red. Es fundamental para verificar si nuestra VM tiene conectividad y qué dirección IP ha obtenido para poder acceder a ella vía SSH más adelante.

## 4. Instalación de Windows 10/11 en VM
El proceso es similar, pero requiere prestar atención a:
- La creación de la cuenta de usuario (local vs Microsoft).
- La instalación de las **Guest Additions** para mejorar el rendimiento gráfico y compartir carpetas.
