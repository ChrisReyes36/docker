# Configuración de Volúmenes y Red para Bases de Datos con Docker

Este proyecto utiliza **Docker** para gestionar servicios de bases de datos y herramientas administrativas. Se crean **volúmenes persistentes** y una **red personalizada** para asegurar la persistencia de datos y permitir la comunicación entre contenedores.

---

## ⚙️ Configuración Inicial

Antes de levantar los contenedores, ejecuta los siguientes comandos en tu terminal:

### 🗃️ Crear volúmenes

```bash
docker volume create pd-data
docker volume create pg-admin
```

### 🛜 Crear red

```bash
docker network create bases-de-datos
```
