# 🏋️‍♂️ FitLife Gym — Implantación de Sistemas Operativos
### Proyecto Intermodular ASIR · Módulo 0369

---

## 📌 Descripción

Diseño e implantación de una infraestructura informática básica para un gimnasio (**FitLife Gym**).  
El proyecto simula un entorno real de empresa en el que se aplican conocimientos de administración de sistemas: instalación, configuración y gestión de sistemas operativos en red.

---

## 🎯 Objetivos

- Analizar las necesidades tecnológicas de una empresa real
- Diseñar una infraestructura informática servidor-cliente
- Implantar sistemas operativos en servidor y equipos cliente
- Configurar red, usuarios y permisos según roles
- Implementar servicios básicos (SSH, compartición de archivos)
- Documentar todo el proceso de implantación

---

## 🖥️ Infraestructura

| Máquina | Sistema Operativo | Rol |
|---|---|---|
| Servidor | Ubuntu Server | Gestión central, SSH, archivos compartidos |
| Cliente 1 | Windows | Recepcionista |
| Cliente 2 | Windows | Entrenador |

Todos los equipos están conectados en una **red local (LAN)** mediante VirtualBox.

---

## ⚙️ Tecnologías utilizadas

- **VirtualBox** — Virtualización de los equipos
- **Ubuntu Server** — Sistema operativo del servidor
- **Windows** — Sistema operativo de los clientes
- **SSH (OpenSSH)** — Acceso remoto al servidor
- **Samba / permisos Linux** — Compartición de archivos

---

## 📂 Estructura del repositorio

```
/proyecto-asir
 ├── README.md
 ├── analisis/
 │    └── analisis_necesidades.md
 ├── plan_implantacion/
 │    └── plan_implantacion.md
 ├── instalacion/
 │    └── instalacion_so.md
 ├── configuracion/
 │    └── configuracion_sistema.md
 ├── usuarios/
 │    └── gestion_usuarios.md
 ├── servicios/
 │    └── servicios_sistema.md
 └── capturas/
      ├── instalacion/
      ├── configuracion/
      ├── usuarios/
      └── servicios/
```

---

## 🔧 Funcionalidades implementadas

- ✅ Instalación de Ubuntu Server y Windows en máquinas virtuales
- ✅ Configuración de red (IP estática en servidor, DHCP en clientes)
- ✅ Gestión de usuarios y grupos según roles del gimnasio
- ✅ Control de permisos por carpetas y grupos
- ✅ Acceso remoto mediante SSH
- ✅ Compartición de archivos internos

---

## 👥 Usuarios y roles

| Usuario | Grupo | Permisos |
|---|---|---|
| `admin` | `grupo_admin` | Acceso total al sistema |
| `recepcion` | `grupo_recepcion` | Acceso a archivos administrativos |
| `entrenador` | `grupo_entrenadores` | Acceso limitado a recursos básicos |

---

## 🔧 Comandos clave utilizados

```bash
# Creación de usuarios
sudo adduser recepcion
sudo adduser entrenador

# Creación de grupos
sudo groupadd grupo_recepcion
sudo groupadd grupo_entrenadores

# Asignación de usuarios a grupos
sudo usermod -aG grupo_recepcion recepcion
sudo usermod -aG grupo_entrenadores entrenador

# Carpeta compartida
mkdir /compartido
chmod 770 /compartido

# SSH
sudo apt install openssh-server
sudo systemctl status ssh
```

---

## 📸 Evidencias

La carpeta `capturas/` contiene pantallazos de:

- Instalación de Ubuntu Server y Windows
- Configuración de red en ambos sistemas
- Creación de usuarios y grupos en Linux
- Gestión de permisos en carpetas
- Estado activo del servicio SSH
- Usuarios creados en equipos Windows cliente

---

## 📈 Resultado

Se ha obtenido una infraestructura funcional que simula un entorno real de empresa, con gestión de usuarios, recursos compartidos y servicios de red operativos.

---

## 🚀 Mejoras futuras

- Implementación de dominio con Active Directory
- Mayor seguridad en accesos (autenticación por clave SSH)
- Automatización de tareas con scripts Bash
- Ampliación con nuevos servicios (DNS, DHCP dedicado)
