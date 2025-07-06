# Challenge1-Alura-One
___________________________________________________________________________________________________
Informe del Challenge N°1 del Programa Oracle ONE (Especialización en Data Science) - Alura Latam. 

**“Análisis del desempeño de cuatro tiendas de artículos electrónicos y del hogar"**


Fecha: 03-07-2025
Autora: Oriana Ortiz N.
___________________________________________________________________________________________________

**1. Introducción**
____________________________________________________________________________________________________
<div align="center">
Dentro del programa Oracle ONE (Oracle Next Education) - Alura Latam, la realización de una serie de Challenges se contempla como una parte fundamental de la formación de los becarios. Esta metodología de aprendizaje, desarrollada por Apple, se basa en exponer a los alumnos a situaciones reales y complejas.
El presente Challenge se enfoca en el análisis descriptivo de datos de cuatro empresas de venta de artículos electrónicos y del hogar, propiedad del Señor Joao. Su objetivo principal es resumir y visualizar las características clave del desempeño de las tiendas, sirviendo como una base fundamental para comprender su situación actual e identificar patrones, tendencias y anomalías en sus operaciones. La meta es determinar, basándose en la información disponible, cuál de las tiendas presenta el menor desempeño para su eventual venta y así apoyar nuevas inversiones.
El equipo de Alura Latam proporcionó una base de datos para cada tienda, todas con una estructura similar. Las tiendas están ubicadas en Bogotá, Colombia, y realizan envíos a prácticamente todo el país. Los requisitos mínimos del Challenge incluían el análisis de facturación, ventas por categoría, calificación promedio de la tienda, productos más y menos vendidos y el costo de envío, abarcando un período de tiempo de aproximadamente tres años.
Inicialmente, los resultados de estos análisis no fueron concluyentes para la selección de la tienda a vender por el Sr. Joao. Por lo tanto, se decidió complementar el estudio con análisis adicionales, enfocados en el comportamiento más reciente del desempeño de las tiendas, utilizando información de la misma base de datos proporcionada por Alura Latam. Estos análisis se acompañan de visualizaciones que facilitan una mejor comprensión de la situación.
Para los análisis se utilizó el lenguaje de programación Python y sus módulos Pandas y NumPy. Las visualizaciones se realizaron con las librerías Matplotlib, Seaborn y Contextily.
En este documento (README.md) se presenta la metodología utilizada en el análisis, una discusión de los resultados obtenidos y recomendaciones clave dirigidas al propietario de las tiendas. Todos los resultados detallados y el código completo están documentados en el cuaderno AluraStoreLatam.ipynb (Jupyter Notebook en Google Colab) que acompaña este README en este mismo repositorio.
</div>


**2. Metodología**
____________________________________________________________________________________________________
El análisis de datos se llevó a cabo utilizando Python (versión 3.11.13) y un conjunto de librerías especializadas. Para el procesamiento y las operaciones numéricas, se emplearon Pandas y NumPy. Las visualizaciones se generaron con Matplotlib y Seaborn, complementadas con Contextily para gráficos que incorporan contexto geográfico. Todo el trabajo se realizó en el entorno de Google Colab.
Las bases de datos, proporcionadas por Alura Latam, consisten en cuatro archivos en formato CSV. Cada archivo corresponde a una tienda independiente, cuyos DataFrames se denominan en este trabajo como “tienda1”, “tienda2”, “tienda3” y “tienda4”, respectivamente. Cada conjunto de datos contenía 12 columnas y 2359 registros, sin valores nulos.
Para este análisis, se asumió que los datos proporcionados ya estaban limpios, por lo que no se realizó una revisión específica de este punto.
Las columnas presentes en cada DataFrame son las siguientes:
- Producto
- Categoría del Producto
- Precio
- Costo de envío
- Fecha de Compra
- Vendedor 
- Lugar de Compra
- Calificación
- Método de pago
- Cantidad de cuotas
- lat (latitud del lugar de compra)
- lon (longitud del lugar de compra)

Es importante indicar que la columna Fecha de Compra no se encontraba en formato de fecha. Por lo tanto, se convirtió a tipo “datetime64[ns]” para todos los DataFrames antes de iniciar cualquier análisis. Las demás columnas se trabajaron sin modificaciones.

Inicialmente, el equipo de Alura solicitó los siguientes análisis:
1) Análisis de facturación 
2) Ventas por categoría 
3) Calificación promedio de cada  tienda, 
4) Productos más y menos vendidos
5) Costo de envío de los diferentes productos

Tras realizar estos análisis iniciales, se determinó que no eran concluyentes para identificar la tienda de menor desempeño. Por ello, se decidió realizar cuatro análisis adicionales aprovechando la información disponible en los DataFrames que no había sido considerada previamente:

6) Método de pago
7) Temporalidad de las ventas
8) Área geográfica de influencia de cada tienda
9) Desempeño de los equipos de trabajo

Para cada uno de los análisis, se desarrolló un código Python específico para el conjunto de datos “tienda1”. Dada la estructura consistente de los DataFrames (mismos nombres de columnas y tipos de registros) para las demás tiendas, este código se replicó sistemáticamente utilizando ciclos for o funciones, aplicando el mismo análisis a los datasets “ tienda2”’, “‘tienda3” y “tienda4”.

El código desarrollado y las visualizaciones pueden ser consultados en el notebook adjunto, siguiendo el índice de los análisis, presentado en este documento

Para facilitar la comprensión y comparación de los resultados, se generaron gráficos para los análisis de 'Productos más y menos vendidos' y 'Temporalidad de las ventas'. Siguiendo la misma lógica de los análisis previos, se desarrolló un código inicial para visualizar los datos de la Tienda 1, el cual se adaptó posteriormente para consolidar la visualización de las cuatro tiendas en una única representación.
En el caso del análisis de la 'Área geográfica de influencia de cada tienda', se utilizaron las librerías Matplotlib, Seaborn y Contextily para ubicar geográficamente los envíos de cada tienda en gráficos individuales.

Posteriormente, dado que el análisis de la temporalidad de las ventas mostró cambios importantes en las tendencias observadas durante el período más reciente —correspondiente a los cuatro últimos trimestres—, se elaboró un gráfico comparativo de las cuatro tiendas, mostrando las ventas por lugar de compra. Este se complementó con un análisis del desempeño de los equipos de trabajo para el mismo marco temporal.

**4. Discusión de los resultados** 
______________________________________________________________________________________________________________________
La revisión del “Análisis de Facturación” —uno de los resultados solicitados por Alura Latam— reveló que, si bien la Tienda 4 exhibe el nivel más bajo de ingresos totales acumulados en los últimos tres años, las diferencias entre los ingresos de las tiendas no son lo suficientemente significativas como para justificar una conclusión drástica basada únicamente en esta métrica. Esto sugiere que ninguna tienda presenta un desempeño excepcionalmente deficiente o sobresaliente en términos de volumen de ingresos que la diferencie marcadamente del resto.

En cuanto a las 'Ventas por Categoría' por tienda, se identifica una tendencia común: las cuatro tiendas exhiben sus mayores ventas en la categoría de 'Muebles'. Un hallazgo clave es que la valoración media por tienda es prácticamente idéntica en todos los casos. Esto sugiere una consistente satisfacción general del cliente con los productos ofrecidos en todos los establecimientos, a pesar de otras posibles variaciones.

Un punto de divergencia significativo se encuentra en los productos más vendidos individualmente por tienda. Aunque la cantidad de unidades vendidas de los productos estrella puede ser similar, los tipos de productos que dominan las ventas difieren notablemente entre cada establecimiento. Esto sugiere que cada tienda podría atender a una clientela con preferencias de producto ligeramente distintas o poseer una especialización implícita.

Finalmente, al considerar el costo de envío del producto, se observa que la Tienda 1 presenta los costos más elevados en esta categoría. No obstante, es crucial destacar que este factor no parece afectar su desempeño en ventas, lo que sugiere que los clientes de la Tienda 1 están dispuestos a asumir ese costo adicional o que otros factores positivos compensan esta diferencia.

Basado exclusivamente en las métricas analizadas hasta este punto, la sugerencia de cerrar la Tienda 4 debido a su menor nivel de ingresos es prematura. Si bien es el establecimiento con el rendimiento más bajo en esa métrica particular, la ausencia de una diferencia abrumadora en los ingresos totales entre las tiendas, sumada a las fortalezas compartidas en ciertas categorías (como 'Muebles'), la consistente valoración media del cliente y las peculiaridades en los productos más vendidos que no se traducen necesariamente en bajo rendimiento, indica que estos datos no son determinantes por sí solos para tomar una decisión de su venta.

En base a estos hallazgos iniciales, y con el fin de obtener una visión más concluyente, se decidió realizar cuatro análisis adicionales, detallados en la metodología. En cuanto al método de pago, este no mostró diferencias significativas entre las tiendas en relación con las ventas en múltiples cuotas. Sin embargo, el análisis de la temporalidad de las ventas sí reveló tendencias interesantes:
  - La Tienda 3 experimentó una abrupta caída en las ventas durante el último trimestre.
  - La Tienda 4 también mostró un descenso, aunque leve, en esta métrica.
  - La Tienda 1 exhibe tendencias muy variables en sus ventas; no obstante, a pesar de estas fluctuaciones, sus ventas siempre se mantienen más altas en comparación con las demás tiendas.
  - La Tienda 2, por su parte, se presenta como la más estable a lo largo del tiempo, manteniendo consistentemente un alto nivel de ventas.

De acuerdo con los gráficos de distribución geográfica de las ventas por tienda durante el último año, se observa una pauta similar para todas: las ventas se concentran en la ciudad de Bogotá (alrededor del 40%), seguidas por Medellín y Cali con porcentajes importantes, y el resto distribuido en otras localidades del país. Un punto interesante es que la distribución de ventas de la Tienda 3 es bastante similar a la de la Tienda 1 (la de mejor desempeño), mientras que la Tienda 4 presenta una distribución más diversificada, con mayores porcentajes en Medellín, especialmente en Cali, y en las restantes localidades.

En cuanto al desempeño de los equipos de trabajo, se encontró que, si bien todas las tiendas cuentan con 13 trabajadores, el rendimiento individual en ventas es muy variable. Sin embargo, todos los miembros del equipo mantienen una buena calificación, lo que indica que no hay diferencias significativas en este aspecto entre las tiendas.

**5.Recomendación**
____________________________________________________________________________________________________________________
En base al análisis descriptivo realizado sobre las cuatro tiendas, mi recomendación para el Señor Joao, respecto a su decisión de vender una de ellas, es la siguiente:
Posponer la decisión de vender una tienda e invertir en análisis adicionales más profundos.
Por los siguiente motivos:
- No hay una tienda claramente de bajo rendimiento: los análisis muestran que, si bien la Tienda 4 registra los ingresos acumulados más bajos en los últimos tres años, las diferencias en los ingresos entre todas las tiendas no son drásticamente significativas. Ninguna tienda destaca como una candidata obvia para la venta basándose únicamente en el volumen de ingresos.
- Fortalezas compartidas: Todas las tiendas muestran fortalezas en áreas clave, como altas ventas en la categoría de 'Muebles' y una satisfacción del cliente consistentemente buena (valoraciones promedio similares). Esto indica una base de negocio saludable en todas las sucursales.
- Matices en el rendimiento: Aunque se observan diferencias (por ejemplo, las ventas altas pero fluctuantes de la Tienda 1, la estabilidad de la Tienda 2, la reciente caída de la Tienda 3 o las ventas geográficamente más diversificadas de la Tienda 4), estas son observaciones descriptivas. No son, por sí solas, indicadores de fallos sistémicos o de potencial inexplorado sin una investigación adicional.
- Limitaciones del análisis descriptivo: el análisis descriptivo nos dice qué pasó, pero no por qué ni qué pasará. Una decisión tan importante como vender una tienda —un activo significativo— requiere comprender las causas de las variaciones de rendimiento (análisis diagnóstico), predecir la rentabilidad futura (análisis predictivo) y evaluar la verdadera salud financiera de cada sucursal (un análisis financiero/de rentabilidad específico).
  
Para tomar una decisión informada, recomiendo al Señor Joao considerar las siguientes acciones:

- Realizar un Análisis Diagnóstico: Investigar las razones subyacentes de las tendencias observadas, como la caída repentina en las ventas de la Tienda 3 en el último trimestre, o los costos de envío más altos de la Tienda 1. Esto podría implicar analizar la competencia local, los esfuerzos de marketing, los cambios operativos o eventos específicos.
- Llevar a cabo un Análisis Integral de Rentabilidad/Financiero: Más allá de solo los ingresos, es crucial evaluar la rentabilidad neta de cada tienda. Esto implicaría calcular los márgenes brutos, los gastos operativos (alquiler, salarios, servicios específicos de cada tienda) y el retorno de la inversión (ROI) general para cada ubicación. Una tienda con menores ingresos brutos podría ser más rentable debido a costos operativos más bajos, o viceversa.
- Pronosticar el Rendimiento Futuro: Utilizar análisis predictivos para proyectar las ventas y la rentabilidad de cada tienda durante los próximos 1 a 3 años. Esto puede ayudar a identificar qué tienda tiene el mejor potencial de crecimiento, independientemente de su rendimiento pasado.
- Revisión Estratégica del Mercado: Analizar el potencial de mercado de la principal área geográfica de cada tienda. Quizás las ventas más diversificadas de la Tienda 4, aunque menores en Bogotá, indiquen un potencial no explotado en otras ciudades como Medellín o Cali que podría capitalizarse con estrategias específicas.

En resumen, si bien el análisis proporciona información inicial muy valiosa, sugiere firmemente que se necesitan más datos y enfoques analíticos más profundos antes de tomar una decisión definitiva sobre la venta de cualquiera de las tiendas. Los datos actuales apuntan a una operación general relativamente saludable, por lo que una decisión precipitada podría ser perjudicial.



