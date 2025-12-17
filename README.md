## 📌 Descripción del Proyecto
Este proyecto consiste en el diseño, simulación y validación de una infraestructura de red escalable para "MIEMPRESA", una corporación transnacional con sede central en Perú. El objetivo principal fue migrar una infraestructura obsoleta (legacy) a una arquitectura jerárquica capaz de soportar operaciones en 5 sedes geográficas (Lima, La Libertad, Ica, Huánuco y Puno).

La solución fue simulada utilizando **Cisco Packet Tracer**, implementando enrutamiento avanzado, políticas de seguridad y despliegue de servicios TI para garantizar alta disponibilidad y continuidad del negocio.

## 🏗 Arquitectura de Red

### Diseño de Topología
* **Topología WAN:** Modelo *Hub and Spoke* conectando la Sede Central (Lima) con 4 sucursales mediante enlaces redundantes.
* **Diseño LAN:** Modelo Jerárquico de 3 Capas (Núcleo, Distribución, Acceso) para la sede principal y diseño colapsado para sucursales.
* **Redundancia ISP:** Configuración de conmutación por error (Failover) con enlaces primarios y secundarios para asegurar la salida a Internet.

## ⚙️ Tecnologías y Configuraciones Clave

### 1. Direccionamiento y Enrutamiento
* **VLSM (Máscara de Subred de Longitud Variable):** Asignación eficiente de IPs (RFC 1918 - `172.21.0.0/16`) para optimizar el espacio de direcciones.
* **Protocolos de Enrutamiento:**
    * **RIPv2:** Utilizado para la convergencia dinámica del enrutamiento interno.
    * **Enrutamiento Estático:** Configurado para la puerta de enlace predeterminada y redundancia hacia Internet.
    * **Enrutamiento Inter-VLAN:** Configuración *Router-on-a-Stick* para la comunicación entre departamentos.

### 2. Conmutación y Segmentación (Switching)
* **VLANs:** Aislamiento de tráfico para diferentes unidades organizacionales:
    * Administración, Logística, Finanzas, Marketing, Ventas.
    * Servidores y Gestión (VLAN Nativa).
* **Wireless:** Despliegue de SSIDs separados para "Ejecutivos" (red interna) y "Clientes" (acceso invitados).

### 3. Servicios de Red
Implementación y simulación de servicios TI esenciales:
* **DHCP:** Asignación automática de IPs para usuarios LAN y WiFi.
* **DNS y HTTP:** Servidor Web interno alojando el dominio corporativo `www.nebulanet.com`.
* **FTP:** Servidor de archivos con restricciones de acceso geográfico (ej. Usuarios de sucursal solo acceden a su FTP local y al de la sede central).
* **Email (SMTP/POP3):** Configuración de servicio de correo corporativo.

### 4. Seguridad
* **ACLs (Listas de Control de Acceso):** Filtrado de Capa 3 para restringir accesos no autorizados a VLANs de servidores críticos.
* **SSH:** Gestión remota segura configurada en todos los routers y switches.
* **Seguridad de Puerto:** Medidas básicas de seguridad en Capa 2.

## ☁️ Análisis de Factibilidad Cloud
Como parte del proyecto, se realizó un dimensionamiento técnico-económico evaluando soluciones en **AWS** y **Azure**. El estudio propuso un modelo híbrido utilizando almacenamiento en la nube para soluciones de backup, reemplazando hardware on-premise para optimizar costos y escalabilidad.

## 🛠️ Herramientas Utilizadas
* **Simulación:** Cisco Packet Tracer 8.x
* **Diagramas:** Figma / Vista lógica de Packet Tracer
* **Documentación:** Excel (Planificación IP) y Word (Informe Técnico)

---
*Proyecto Universitario - UPC - Ingeniería de Sistemas de Información*
