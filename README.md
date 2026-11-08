# Tienda H&M

Esta version del proyecto esta usando docker, para ver el archivo original visitar https://github.com/Crls-Guerrero/clone-store-hym

Ejecución con Docker (recomendada)

Requisitos previos

- Docker Desktop (en Windows requiere WSL2)
- SSMS u otro cliente SQL, solo para importar la base la primera vez

Variables de entorno

- Crea un .env y reemplaza la informacion de .env.example (.env nunca se sube a Git (está en .gitignore) solo .env.example queda como plantilla.)
- Define una contraseña segura para SQL Server (mayúsculas, minúsculas, números y un símbolo).

### Primera vez

1. Levanta solo la base de datos:

   ```bash
   docker compose up -d sqlserver
   ```

2. Espera unos 20 segundos y conéctate con SSMS:
   - Servidor: `localhost,1434`
   - Autenticación: SQL Server Authentication
   - Usuario: `sa`
   - Contraseña: la de tu `.env`

3. Ejecuta `database/TiendaHYM_docker.sql`. Crea la base `TiendaHYM`, sus tablas y los datos de ejemplo.

4. Levanta el resto de los servicios:

   ```bash
   docker compose up -d
   ```

# Comandos útiles

docker compose ps (estado de los servicios)
docker compose logs backend (logs del backend)
docker compose up -d --build backend (reconstruir el backend tras cambiar código)
