# IGN_INDEC_georef

Los codigos en este repositorio relacionan las entidades espaciales de los últimos censos de Argentina (1991, 2001, 2010, INDEC) con las referencias del Instituto Geográfico Nacional (IGN).

### Instalacion de modulos de python

Para utilizar este repositorio, es necesario instalar los siguientes módulos de Python:

  - Pyunpack
  - Patool
  - Geopandas

Estos módulos se pueden instalar fácilmente con pip.

### Instalación en Windows

En Windows, es posible que sea necesario descargar y utilizar los archivos whl correspondientes a tu versión de Python (www.lfd.uci.edu/~gohlke/pythonlibs/).

Si se produce un error al instalar Fiona con el archivo whl, es necesario instalar Fiona a partir del fuente (source). Para hacer esto, descarga el archivo tar.gz, extrae su contenido y ejecuta el siguiente comando desde la carpeta:

`python setup.py build_ext -I<path to gdal include files> -lgdal_i -L<path to gdal library> install --gdalversion X.X`

por ejemplo:
`python setup.py build_ext -IC:\user\anaconda3\Lib\site-packages\osgeo\include\gdal -lgdal_i -LC:\user\anaconda3\Lib\site-packages\osgeo\lib install --gdalversion 3.2.1`

Además, es necesario configurar las variables de entorno de Windows correspondientes a GDAL. Para hacer esto, haz clic derecho en "Mi PC" y selecciona "Propiedades" -> "Configuración avanzada del sistema" -> "Variables de entorno" ('Advanced system settings'> 'Environment Variables...'). Agrega las siguientes variables:

- GDAL_DATA = C:\user\anaconda3\Lib\site-packages\osgeo\data\gdal

- PROJ_LIB = C:\Users\BCNCPC23\anaconda3\Lib\site-packages\osgeo\data\proj

Para instalar geopandas, descarga el archivo tar.gz y ejecuta el siguiente comando desde la carpeta donde lo hayas extraído:

`python setup.py build_ext`
