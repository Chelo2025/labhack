#  Ethical Hacking: OWASP Juice Shop + Kali Linux

Un entorno de laboratorio controlado, seguro y portátil para prácticas de Ethical Hacking y Pentesting Web. Este proyecto despliega automáticamente una víctima vulnerable (OWASP Juice Shop) y una máquina atacante (Kali Linux) en una red aislada utilizando Docker.


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
    
    git clone https://github.com/Chelo2025/labhack.git
    
    cd labhack
    

3.  **Crear el directorio para persistencia:**
    El contenedor de Kali guarda los reportes en un volumen local. Crea la carpeta antes de iniciar:
    
    mkdir mis-reportes
    

4.  **Iniciar el laboratorio:**
    Ejecuta el siguiente comando para descargar las imágenes y levantar los servicios en segundo plano:
    
    docker compose up -d
    

---

##  Uso del Laboratorio

### 1. Acceso a la Víctima (Juice Shop)
La aplicación web vulnerable está expuesta en el puerto `3000` de tu máquina local (host).

* **URL:** [http://localhost:3000](http://localhost:3000)

### 2. Acceso al Atacante (Kali Linux)
Kali Linux se ejecuta en modo interactivo pero sin interfaz gráfica (headless) para ahorrar recursos. Para acceder a la terminal:


docker exec -it lab_attacker /bin/bash


---

## Autor

### Marcelo Martinez - Chelo2025

🎓 Estudiante de Licenciatura en Tecnologías Digitales

🛡️ Técnico Superior en Redes Informáticas

🎓 Estudiante en Diplomado en Administración de Redes Linux con Orientación en Ciberseguridad y Ethical Hacking con Kali Linux.
