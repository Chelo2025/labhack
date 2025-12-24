#  Dockerized Ethical Hacking Lab: OWASP Juice Shop + Kali Linux

Un entorno de laboratorio controlado, seguro y portátil para prácticas de Ethical Hacking y Pentesting Web. Este proyecto despliega automáticamente una víctima vulnerable (OWASP Juice Shop) y una máquina atacante (Kali Linux) en una red aislada utilizando Docker.

##  Tabla de Contenidos
- [Arquitectura del Laboratorio](#-arquitectura-del-laboratorio)
- [Requisitos Previos](#-requisitos-previos)
- [Instalación y Despliegue](#-instalación-y-despliegue)
- [Uso del Laboratorio](#-uso-del-laboratorio)
  - [Acceso a la Víctima](#1-acceso-a-la-víctima-juice-shop)
  - [Acceso al Atacante](#2-acceso-al-atacante-kali-linux)
- [Configuración Técnica](#-configuración-técnica)
- [Disclaimer](#-disclaimer)

---

##  Arquitectura del Laboratorio

El entorno consta de dos contenedores principales conectados a través de una red bridge interna (`hacking-net`):

| Servicio | Rol | Imagen | Descripción |
| :--- | :--- | :--- | :--- |
| **victim-juice** |  Objetivo | `bkimminich/juice-shop` | Aplicación web moderna intencionalmente vulnerable (OWASP Top 10). |
| **attacker-kali** |  Atacante | `kalilinux/kali-rolling` | Distribución Linux con herramientas de seguridad ofensiva. |

---

##  Requisitos Previos

Necesitas tener instalado en tu sistema:
* **Docker**
* **Docker Compose**

---

##  Instalación y Despliegue

1.  **Clonar este repositorio:**
    ```bash
    git clone [https://github.com/TU_USUARIO/TU_REPO.git](https://github.com/TU_USUARIO/TU_REPO.git)
    cd TU_REPO
    ```

2.  **Crear el directorio para persistencia:**
    El contenedor de Kali guarda los reportes en un volumen local. Crea la carpeta antes de iniciar:
    ```bash
    mkdir mis-reportes
    ```

3.  **Iniciar el laboratorio:**
    Ejecuta el siguiente comando para descargar las imágenes y levantar los servicios en segundo plano:
    ```bash
    docker-compose up -d
    ```

---

##  Uso del Laboratorio

### 1. Acceso a la Víctima (Juice Shop)
La aplicación web vulnerable está expuesta en el puerto `3000` de tu máquina local (host).

* **URL:** [http://localhost:3000](http://localhost:3000)

### 2. Acceso al Atacante (Kali Linux)
Kali Linux se ejecuta en modo interactivo pero sin interfaz gráfica (headless) para ahorrar recursos. Para acceder a la terminal:

```bash
docker exec -it lab_attacker /bin/bash
