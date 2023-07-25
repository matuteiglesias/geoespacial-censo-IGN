# Datos espaciales: Radios Censales, Fracciones, en Departamentos IGN

Este repositorio contiene scripts de procesamiento de datos para la manipulación y reconciliación de información geográfica de los últimos censos de Argentina (1991, 2001, 2010, INDEC) con las referencias del Instituto Geográfico Nacional (IGN) de Argentina.

## Descripción

El repositorio se compone de tres scripts de Jupyter notebook que realizan las siguientes tareas:

- **Descarga de geometrías (IGN, Censo - CEUR CONICET)**: Este script se encarga de descargar las geometrías de radios censales de las fuentes mencionadas.

- **Dissolver de áreas del censo**: Este script realiza un proceso de disolución de las áreas del censo a nivel de fracciones censales y departamentos. Esto significa que las geometrías se agrupan y combinan en base a atributos comunes.

- **Reconciliación de información geográfica**: Este script se encarga de la tarea crítica de reconciliar la información geográfica de las dos fuentes de datos. Se realiza una intersección espacial para ajustar las geometrías de los radios censales del CONICET con las áreas geográficas del IGN en los casos con problemas o inconsistencia en ids de lugares.

*El producto principal de este repositorio es el archivo `radios_IGN_<year>`, que se guarda después de ejecutar el tercer script. Este archivo contiene geometrías conciliadas a varios niveles geográficos, incluyendo provincias, departamentos, fracciones censales y radios censales. Tiene un total de 52,401 unidades geográficas únicas, lo que lo hace extremadamente útil para una variedad de análisis geoespaciales.*

## Contribuciones

Las contribuciones a este repositorio son bienvenidas. Si encuentra algún error o tiene alguna sugerencia no dude en abrir issue, pull request o contactarse.

## Contacto

Si tenes cualquier pregunta sobre este repositorio o necesitas ayuda, no dudes en escribime matuteiglesias@gmail.com.


#### Instalación de Geopandas en Windows

Es posible que encuentres problemas al instalar Geopandas en Windows. Aquí te proporcionamos algunos pasos que podrían ayudarte a resolver estos problemas. Recuerda que estos pasos son necesarios si quieres ejecutar los scripts de este repositorio en tu máquina local. Si sólo estás interesado en los datos procesados, puedes usar directamente los archivos `radios_IGN_...`.

Pasos para solucionar problemas de instalación de Geopandas:
- Descarga los archivos .whl: En Windows, puede ser necesario descargar y utilizar los archivos .whl correspondientes a tu versión de Python. Puedes encontrar estos archivos en 
(www.lfd.uci.edu/~gohlke/pythonlibs/).

- Instalación de Fiona:** Si se produce un error al instalar Fiona con el archivo .whl, necesitarás instalar Fiona a partir del código fuente. Para hacer esto, descarga el archivo tar.gz de Fiona, extrae su contenido y ejecuta el siguiente comando desde la carpeta donde lo hayas extraído:

`python setup.py build_ext -I<path to gdal include files> -lgdal_i -L<path to gdal library> install --gdalversion X.X`

por ejemplo:

`python setup.py build_ext -IC:\user\anaconda3\Lib\site-packages\osgeo\include\gdal -lgdal_i -LC:\user\anaconda3\Lib\site-packages\osgeo\lib install --gdalversion 3.2.1`

- Configuración de las variables de entorno de GDAL: También necesitarás configurar las variables de entorno de Windows correspondientes a GDAL. Para hacer esto, haz clic derecho en "Mi PC" y selecciona "Propiedades" -> "Configuración avanzada del sistema" -> "Variables de entorno" ('Advanced system settings'> 'Environment Variables...'). Agrega las siguientes variables:

`GDAL_DATA = C:\user\anaconda3\Lib\site-packages\osgeo\data\gdal`

`PROJ_LIB = C:\Users\BCNCPC23\anaconda3\Lib\site-packages\osgeo\data\proj`

- Instalación de Geopandas: Finalmente, para instalar Geopandas, descarga el archivo tar.gz de Geopandas y ejecuta el siguiente comando desde la carpeta donde lo hayas extraído:
  
`python setup.py build_ext`
