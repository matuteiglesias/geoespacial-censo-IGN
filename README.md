# IGN_INDEC_georef

Los codigos en este repositorio relacionan las entidades espaciales de los ultimos censos de Argentina (1991, 2001, 2010, INDEC) con las referencias del Instituto Geografico Nacional (IGN).

### Instalacion de modulos de python

Puede que deba instalar los modulos:

  - pyunpack, patool

Para descargar y extraer los shapefile de Censos (radios censales).

  - geopandas

*GeoPandas is a geospatial extension to Python data analysis library Pandas. It builds upon Shapely, Fiona, PyProj, Matplotlib, and Descartes, all of which must be installed.*

Por lo general estos modulos se pueden instalar simplemente con pip.

En el caso de Windows, usando los archivos whl (www.lfd.uci.edu/~gohlke/pythonlibs/) correspondientes a tu version de python. 

Instalar fiona en windows con el whl puede dar error debido a que faltara cierta info referida al modulo GDAL que vamos a tener que introducir manualmente. En ese caso debemos instalar Fiona y a partir del fuente (source). Para eso, descargar el archivo tar.gz, extraerlo, entrar a la carpeta y correr algo como:

`python setup.py build_ext -I<path to gdal include files> -lgdal_i -L<path to gdal library> install --gdalversion X.X`

por ejemplo:
`python setup.py build_ext -IC:\user\anaconda3\Lib\site-packages\osgeo\include\gdal -lgdal_i -LC:\user\anaconda3\Lib\site-packages\osgeo\lib install --gdalversion 3.2.1`

Consultar la documentacion en https://pypi.org/project/Fiona/. 

Para que funcione fiona debemos configurar las variables de environment referidas a GDAL en las opciones de windows. Boton derecho en Mi PC 'Advanced system settings'> 'Environment Variables...' y ahi agregar las variables:

GDAL_DATA = C:\user\anaconda3\Lib\site-packages\osgeo\data\gdal
PROJ_LIB = C:\Users\BCNCPC23\anaconda3\Lib\site-packages\osgeo\data\proj

Descargar el archivo tar.gz para geopandas y correr:

`python setup.py build_ext` desde el directorio donde extrajimos geopandas.
