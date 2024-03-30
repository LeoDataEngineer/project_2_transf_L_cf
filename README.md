# Proyecto de trasnformación en dbt.
## Nuevo Servicio para la Aplicación Móvil de Baecobici.com.ar. Se realiza una traformación a partir de dos tablas que existen en snowflake, solicitada por el equido de ML, para predecir la disponiblidad de bicicletas.

## Proceso:
### Se instalara el paquete: `dbt-snowflake`. 

### Se creara la conexión a la base de dato en Snowflake

### Crear el modelo: se crea una tabla final para el posterior  uso del proyecto, que es crear un ML para la apliación movíl.
- El modelo data_processed.sql es un script SQL que selecciona y combina datos de dos tablas, ESTACION y NUM_BICI, en una nueva tabla materializada llamada data_processed. La nueva tabla contiene información sobre las estaciones de bicicletas, incluyendo su ID, nombre, ubicación, capacidad, número de bicicletas disponibles y en servicio, y la fecha y hora en que se reportaron los datos. La tabla resultante solo incluye registros donde el estado de la estación es 'IN_SERVICE'. Este modelo es un ejemplo de cómo se pueden transformar y combinar datos de diferentes tablas en una nueva tabla utilizando SQL en un proyecto de dbt (data build tool).
- Tabla final: [data_processed](https://github.com/leodataengineer/project_2_transf_L_cf/tree/main/models/example/data_processed.sql#L1-L24)


### Algunos archivos importantes:
-  **`profiles.yml`:** El archivo profiles.yml contiene la configuración de perfil para un proyecto de dbt (data build tool). En este caso, el perfil se llama project_final y tiene un entorno de desarrollo (dev) configurado para conectarse a una base de datos Snowflake. La configuración incluye detalles como el nombre de cuenta, base de datos, usuario, contraseña, rol, esquema, almacén y número de hilos. Los valores reales para estos detalles se obtienen de variables de entorno.
-   **`dbt_project.yml`:** El archivo dbt_project.yml es un archivo de configuración principal para un proyecto de dbt (data build tool). Contiene información clave sobre el proyecto, como el nombre, la versión, la configuración de la base de datos y los directorios donde se encuentran los diferentes tipos de archivos del proyecto (modelos, análisis, pruebas, semillas, macros, instantáneas).

### Todo el proceso de tranformación se realiza de forma automatizada, gracias a Github Action.

 Archivo yml del workflow: [transfor.yml](https://github.com/leodataengineer/project_2_transf_L_cf/tree/main/.github/workflows/transfor.yml#L1-L25)

