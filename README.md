Postgres + pgadmin
===

<hr>

**Esta configuración integra la imagen de [Postgres](https://hub.docker.com/_/postgres) y [PgAdmin](https://hub.docker.com/r/elestio/pgadmin)**

## Uso

Para usar esta imagen se debera de seguir los siguientes pasos a continuación:

### Paso 1. Preparar variables de entorno

Se debe de ejecutar el comando:
> cp .env.example .env

Y del archivo `.env` se deberan de completar los datos solicitados tal como se muestra eb la siguiente tabla:

Para la configuración de la base de datos las variables a completar son las siguientes:

| Variable                  | Descripción                               | Links directos                                      |
|---------------------------|-------------------------------------------|-----------------------------------------------------|
| DB_POSTGRES_VERSION       | Version de postgres a utilizar            | [Versiones](https://hub.docker.com/_/postgres/tags) |
| DB_POSTGRES_DATABASE      | Nombre de la base de datos a crear        | N/A                                                 |
| DB_POSTGRES_PORT          | Puerto a exponer en el equipo             | N/A                                                 |
| DB_POSTGRES_USER          | Usuario por defecto en la base de datos   | N/A                                                 |
| DB_POSTGRES_PASSWORD      | Contraseña por defecto del usuario        | N/A                                                 |

Para la configuración del PgAdmin las variables a completar son las siguientes:

| Variable                  | Descripción                                   | Links directos                                      |
|---------------------------|-----------------------------------------------|-----------------------------------------------------|
| MANAGE_PGADMIN_PORT_EXPOSE| Puerto a exponer el pgadmin (en el navegador) | N/A                                                 |
| MANAGE_PGADMIN_EMAIL      | Correo por defecto de acceso al pgadmin       | N/A                                                 |
| MANAGE_PGADMIN_PASSWORD   | Contraseña por defecto de acceso al pgadmin   | N/A                                                 |

### Paso 2. Levantar el contenedor

Para levantar el contenedor es necesario usar el siguiente comando:
> docker compose up --build --force-recreate

Se agrega `--force-recreate` por si ocurrio algun problema esto intentara crearlo nuevamente todo el contenedor.

**Una vez ejecutado el comamando es necesario esperar unos 10 segundos aprox**.

### Paso 3. Acceder al navegador

Si no ocurrio ningun problema el pgadmin estara desplegado
por defecto en: <http://localhost> y si especificaste un puerto
diferente al 80 entonces deberas acceder a: <http://localhost:port>
donde port es lo que especificaste en la variable `MANAGE_PGADMIN_PORT_EXPOSE`.

<hr>

## Requerimientos

* [Docker Desktop](https://www.docker.com/)

## Creditos a sus creadores

* [Elestio](https://hub.docker.com/u/elestio)
* Postgres
