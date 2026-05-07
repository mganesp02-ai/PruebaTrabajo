# Tema 6: Configuración de Red y Servicios Básicos

En el último tema, conectaremos nuestros sistemas a la red y aprenderemos cómo se comunican entre sí.

## 1. Conceptos Básicos de Redes
- **Dirección IP**: El identificador único de cada equipo en la red.
- **Máscara de Subred**: Define qué parte de la IP es la red y qué parte es el host.
- **Puerta de Enlace (Gateway)**: La salida hacia otras redes (Internet).
- **DNS**: Traduce nombres (google.com) a IPs.

## 2. Configuración en Linux
En distribuciones modernas como Ubuntu, la red se gestiona a menudo con **Netplan** o comandos directos.

### Comandos de diagnóstico:
```bash
# Ver la configuración de red detallada
ip addr

# Comprobar conectividad con otro equipo
ping -c 4 8.8.8.8

# Ver la ruta que siguen los paquetes
traceroute google.com
```

> **¿Por qué usar traceroute?**
> Si no tenemos internet, `traceroute` nos dice en qué punto exacto se pierde la conexión (si es en nuestro router, en el ISP o más allá).

## 3. Servicios de Red Comunes
- **DHCP**: Asigna IPs automáticamente.
- **SSH**: Permite administrar servidores de forma remota y segura.
- **Samba/NFS**: Permiten compartir archivos entre Linux y Windows.

## 4. Resolución de Problemas (Troubleshooting)
El flujo lógico ante un problema de red debe ser:
1. ¿Tengo cable/enlace físico?
2. ¿Tengo IP?
3. ¿Llego al router (ping al gateway)?
4. ¿Llego a internet (ping 8.8.8.8)?
5. ¿Funciona el nombre (ping google.com)?
