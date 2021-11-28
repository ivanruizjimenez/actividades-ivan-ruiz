# Visualización datos proyecto TRESCA

## Iván Ruiz Jiménez

### Obtención de datos
La visualización se ha obtenido a partir de los datos obtenidos por el [Proyecto TRESCA](https://github.com/flowsta/nebrija-2021/blob/main/data/tendencias-millonarias-nebrija.csv). Para realizar la actividad, he utilizado **Open Refine** para limpiar los datos y **Datawrapper** para la elaborar la infografía final.
El archivo inicial contiene el volumen de tuits que generaron los mensajes de los cuatro principales políticos estadounidenses, aspirantes en su día a la elección como presidente de Estados Unidos, en esta red social. Son cuatro: por el Partido Demócrata Joe Biden y Kamala Harris; por el Partido Republicano Donald Trump y Mike Pence.

### Open Refine
Con esta herramienta he hecho el trabajo previo de limpieza y selección de datos.
El primer paso, ha sido el de **renombrar las columnas existentes** para mostrar una cabecera más clara y descriptiva.
A continuación, he aplicado una **filtro de texto** en la columna "nombre" para obtener únicamente los resultados de cada uno de los cuatro políticos analizados y **generar una columna** extra a partir de ello. Se puede ver en la siguiente imagen: ![imagendefiltrotexto](meterlinkaquí)

Para agregar la columna la ruta ha sido: **editar columna- agregar columna basada en esta columna**. Y ahí he aplicado esta fórmula: value.strip(),lower() if ="pence" in value: return "Mike Pence" (para el caso de Mike Pence). El resultado se puede observar aquí ![imagentransformacioncolumna](meterlinkaquí).

A continuación, he **limpiado los caracteres que sobraban en la columna "fecha"** para una correcta interpretación. Concretamente, son los valores "T" y "Z", que he sustituido por un espacio y por una cadena vacía respectivamente. La sustitución la he hecho a partir de la ruta editar celda-transformar. con la fórmula value.replace("T"," ").replace("Z",""). ![imagenreemplazarvalores](meterlinkaquí).

Finalmente, he aplicado **transformaciones comunes** a la columna de tuits para indicarle a Open Refine que los datos que tiene son números. No he aplicado lo mismo en la columna fecha tras comprobar que, si lo hacía, no me aplicaba el reemplazo anterior de carateres. Para acabar, he reordenado las columnas. El resultado final ha sido este: ![imagenresultadoopenrefine](meterlinkaquí).

Una de los **condicionantes finales de cara a la visualización** es que no he logrado acotar por fechas. Tal como se puede ver en la imagen, al **aplicar la faceta de línea de tiempo**, el resultado obtenido no ha sido lo esperado, sin que haya sido posible descubrir el por qué. ![imagenfacetalineatiempo](link).



### Datawrapper
Una vez exportado el archivo csv de Open Refine, lo he cargado en Datawrapper. [imagencargaarchivodatawrapper](link)

El gráfico escogido ha sido de tipo lineal para representar el volumen total de interacciones a los tuits de los cuatro políticos entre mayo de 2020 y mayo de 2021, dejando patente un mayor volumen entre octubre de 2020, últimas semanas antes del proceso electoral (noviembre) y finales de enero, momento de la toma de posesión del ganador.

Una de las limitaciones de este gráfico es que no permite ver el **volumen atribuido a cada uno de los cuatro políticos**, sin embargo, no he sido capaz de obtener esa visualización ni descubrir dónde estaba el error. 

El resultado final se puede consultar a continuación ![imagen](https://github.com/ivanruizjimenez/actividades-ivan-ruiz/blob/main/ad-3-ivan-ruiz/img/carga-datawrapper.jpg?raw=true)

<iframe title="Las elecciones de EEUU en Twitter" aria-label="Interactive line chart" id="datawrapper-chart-5ROEQ" src="https://datawrapper.dwcdn.net/5ROEQ/3/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="400"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(e){if(void 0!==e.data["datawrapper-height"]){var t=document.querySelectorAll("iframe");for(var a in e.data["datawrapper-height"])for(var r=0;r<t.length;r++){if(t[r].contentWindow===e.source)t[r].style.height=e.data["datawrapper-height"][a]+"px"}}}))}();
</script>
