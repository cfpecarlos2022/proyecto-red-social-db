proyecto-red-social-db

Este proyecto contiene el esquema de base de datos relacional para una red social, implementado en MySQL / MariaDB. Incluye la estructura de tablas, restricciones de clave foránea con borrado en cascada (ON DELETE CASCADE) y datos de prueba.

📌 Estructura de la Base de Datos

El sistema está compuesto por las siguientes entidades principales:

usuarios: Gestión de usuarios (credenciales, biografía, avatar y estado de verificación).

publicaciones: Contenido publicado por los usuarios con soporte para texto e imagen.

comentarios: Comentarios asociados a las publicaciones.

likes: Registro de reacciones de los usuarios a las publicaciones (clave primaria compuesta usuario_id, publicacion_id).

seguidores: Relación entre usuarios para el sistema de seguimiento/network.

roles: Definición de roles dentro de la plataforma.

🛠️ Tecnologías

SGBD: MySQL 8.0+ / MariaDB

Codificación: utf8mb4 (soporte completo para emojis y caracteres especiales)

🚀 Instalación e Importación

Clonar el repositorio:

git clone https://github.com/tu-usuario/proyecto-red-social-db.git
cd proyecto-red-social-db


Crear la base de datos:

CREATE DATABASE IF NOT EXISTS red_social_db
CHARACTER SET utf8mb4
COLLATE utf8mb4_0900_ai_ci;
USE red_social_db;


Importar el dump SQL:

Desde la consola de MySQL/MariaDB:

mysql -u tu_usuario -p red_social_db < proyecto-red-social-db.sql


O bien desde herramientas gráficas (phpMyAdmin, DBeaver, MySQL Workbench): Selecciona la base de datos red_social_db e importa el archivo proyecto-red-social-db.sql.

📊 Relaciones Clave

Todas las tablas que dependen de usuarios o publicaciones implementan ON DELETE CASCADE. Si se elimina un usuario o una publicación, se limpiarán automáticamente sus comentarios, likes y relaciones asociadas.
