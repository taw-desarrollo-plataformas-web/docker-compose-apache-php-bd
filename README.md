
# Docker Compose: Apache + PHP + Base de Datos

Este repositorio proporciona una configuración básica utilizando Docker Compose para ejecutar un entorno de desarrollo compuesto por Apache, PHP y un servidor de base de datos MariaDB. Está orientado a cursos iniciales de desarrollo web, donde los estudiantes deben ejecutar el entorno de manera local sin necesidad de realizar configuraciones manuales.

## 1. Objetivo del proyecto

Este entorno permite a los estudiantes levantar un ambiente funcional de desarrollo web mediante un solo comando. El stack incluye:

- Servidor Apache con PHP
- Motor de base de datos MariaDB
- Interfaz de administración phpMyAdmin

## 2. Requisitos previos

Los estudiantes deben contar con:

- Docker instalado en el sistema operativo
- Docker Compose integrado (comando `docker compose`)
- Git instalado
- Puertos libres: 8080, 8081 y 3306

## 3. Obtención del repositorio

### Opción A: Realizar un fork (recomendado)

1. Acceder al repositorio original en GitHub.
2. Seleccionar **Fork** para crear una copia personal.
3. Clonar el fork en la computadora local:

```bash
git clone https://github.com/<su-usuario>/<nombre-del-repo>.git
```

### Opción B: Clonar directamente el repositorio

```bash
git clone https://github.com/taw-desarrollo-plataformas-web/docker-compose-apache-php-bd.git
```

## 4. Estructura del proyecto

El repositorio incluye:

```
docker-compose.yml     Archivo de definición de servicios
README.md              Documentación del proyecto
.gitignore             Exclusiones para Git
```

Cuando se ejecute por primera vez, Docker generará automáticamente:

- `mysql_data/` para los datos de MariaDB
- `app/` como directorio raíz del servidor Apache

Estas carpetas no forman parte del repositorio y están excluidas mediante `.gitignore`.

## 5. Verificación de puertos disponibles

En Linux:

```bash
sudo lsof -i :8080
sudo lsof -i :8081
sudo lsof -i :3306
```

Si no se muestra salida, el puerto está libre.

## 6. Ejecución del entorno

```bash
docker compose up -d
```

## 7. Acceso a los servicios

- Aplicación web: http://localhost:8080
- phpMyAdmin: http://localhost:8081

## 8. Detener los servicios

```bash
docker compose down
```

Eliminar volúmenes (incluye datos de la base):

```bash
docker compose down -v
```

## 9. Buenas prácticas

- No modificar el archivo `docker-compose.yml` sin indicaciones.
- No subir al repositorio las carpetas generadas automáticamente (`mysql_data/`, `app/`).
