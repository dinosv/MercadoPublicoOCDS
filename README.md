﻿# Aplicación para almacenar y visualizar compras públicas usando el estándar OCDS.

## Tabla de contenido
  * [Demo](#demo)
  * [Resumen](#resumen)
  * [Motivación](#motivación)
  * [Instalación](#instalación)

## Resumen
Se desarrolla una aplicación en R, que bajo el ingreso de unos pocos parámetros, descarga automáticamente datos masivos de compras públicas en formato OCDS, los almacena en una base de datos Postgress, y permite la visualización en un panel usando Shiny.

## Motivación
Actualmente existe gran interés por parte de distintos actores por información en las compras públicas en Chile. Éstos pueden ser la sociedad civil monitoreando el correcto uso de los fondos públicos, proveedores buscando oportunidades de negocio, entre otros.

A su vez, existen esfuerzos tanto de organizaciones no gubernamentales (ONG) tales como la “Alianza del gobierno abierto” y Open Contracting Partnership (OCP) entre otros, que establecen lineamientos y recomendaciones para democratizar y abrir los datos públicos hacia la ciudadanía, con fines de transparencia y aumentar la participación de éstos en el monitoreo de las acciones gubernamentales.

En esta línea, OCP genera un estándar de modelo de datos a nivel global, que permite generar análisis comparativos de compras públicas en todos los países que lo posean, independiente de la estructura de datos, procesos de compra o nomenclatura de sus datos. La tecnología base recomendada para esto, es a través de archivos JSON, cuya conexión con el usuario es usualmente a través de APIs, por la gran cantidad de datos. 

En favor de lo anterior, ChileCompra adopta los lineamientos de datos abiertos implementando una API con estándar de datos OCDS (Open Contracting Data Standard) propuesto por OCP, que permite a cualquier usuario descargar datos de compras públicas tanto en tiempo real, como a través de descargas masivas de datos, teniendo todas las ventajas que el estándar conlleva.

El problema de los datos provenientes de esta API en particular es la gran barrera de entrada en conocimientos tecnológicos que presenta para los usuarios: El entendimiento del negocio de compras públicas, manipulación de listas anidadas en formato JSON, manejo de softwares especializados en datos, el idioma inglés y la manipulación de archivos pesados (1,3 gigabytes app por archivo mensual.) 

Ante esta problemática, se desarrolla un aplicativo en R cuyo objetivo es servir como “molde” para disminuir algunas de las barreras de entrada en utilización de datos de compras públicas a la ciudadanía, facilitando la extracción, manipulación y visualización de los datos. 

Describiéndolo de manera más específica, el aplicativo desarrollado en R permite la extracción de los archivos de licitaciones en formato OCDS por el usuario, generar un modelo de datos relacionales en una base de datos en PostgreSQL, alimentar tablas relaciones a partir de archivos JSON, utilizar estas mismas tablas para realizar consultas y alimentar un panel con visualizaciones utilizando Shiny, incluyendo métricas de ejemplo que pueden ser de interés tanto para la sociedad civil como para proveedores.

## Instalación
La instalación se divide en distintas etapas:
1. Instalación de R y Rstudio. 
Recomiendo seguir las indicaciones de este video:
[Video explicativo de instalación](https://www.youtube.com/watch?v=rxsE3Uc_bnU)
    - La versión utilizada para R es la 3.5.2
    - Recomiendo la última versión de RStudio

2. Instalación de Postgress
Recomiendo seguir las indicaciones del siguiente video:
[Video explicativo de instalación](https://www.youtube.com/watch?v=cHGaDfzJyY4)
    - Muy importante recordar la constraseña y puerto ingresado.
    - La instalación estándar es suficiente

3. Configuración de aplicativo:

    - Clonar o descargar este repositorio en su computador
	- Ejecutar el archivo: __InstalarPackages.R__
	- Agregar en la aplicación la dirección de las carpetas asociadas
	- Agregar en la aplicación los datos de la conexión a PostgreSQL
	
## Utilización
1. Indicar en archivo __ExtraccionDMV5.R__ los meses a extraer
2. Ejecutar el archivo  __ExtraccionDMV5.R__.
      - Con una muy buena conexión a internet, toma aproximadamente 15 minutos cargar 1 mes de datos.
	  - Para configurar R con task manager, leer el archivo:
	  -  
	  
## Tecnologías utilizadas

[<img target="_blank" src="https://www.r-project.org/logo/Rlogo.svg" width=100>](https://r-project.org/) [<img target="_blank" src="https://wiki.postgresql.org/images/a/a4/PostgreSQL_logo.3colors.svg" width=100>](https://postgresql.org/) 


    
    