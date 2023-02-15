# Laboratorio 1 - Clustering

[Objetivos](#objetivos)

[Herramientas](#herramientas)

[Enunciado](#enunciado)

[Entregables](#entregables)

[Rúbrica de clasificación](#rubrica)

[Sugerencias y aclaraciones](#sugerencias)

## <a name="objetivos"></a> Objetivos

- Aplicar el proceso de aprendizaje para resolver una tarea de agrupación (segmentación o clustering), desde el entendimiento de los daots hasta la interpretación de los resultados. 
- Aplicar tres algoritmos de clustering (k-means y dos de libre elección) para resolver el objetivo de la organización. 
- Determinar los hiperparámetros para la construcción de los modelos dependiendo de los algoritmos utilizados.
- Recomendar el algoritmo más adecuado a la organización con base en una tabla comparativa que muestre el rendimiento de los tres modelos construidos. 
- Derivar conclusiones a partir de los mejores grupos identificados, que sean útiles para la organización.
- Comunicar los hallazgos encontrados a la organización, explicando por qué tienen valor para el negocio.


## <a name="herramientas"></a> Herramientas

Durante este laboratorio trabajaremos con las siguientes herramientas:

 - Python
	 - Distribución sugerida: [Anaconda](https://www.continuum.io/downloads) 
		 - La versión de Anaconda es 4.4
		 - La versión usada es la de python 2.7, usar python 3 no debería requerir muchos cambios.
	 - Ambiente de desarrollo
	   	 - JupyterLab
	   	 - Google Colab
	 - Librerías
	 	 - Pandas
		 - Scikit-learn
		 - Matplot
		 - Seaborn 

## <a name="enunciado"></a> Enunciado

### Descripción de negocio

BiciAlpes es una organización que presta un servicio de alquiler de bicicletas, solidario y con muchos beneficios para los usuarios. Su objetivo es incentivar planes de movilidad sostenible en zonas urbanas, que contribuyan a reducir la emisión de gases de efecto invernadero que afectan la temperatura del planeta. En el último año, han detectado con preocupación que el uso de la bicicleta se está viendo obstaculizado por la falta de información sobre la seguridad en las vías. Piensa que proporcionar a los ciclistas información sobre las rutas más seguras podría contribuir a aumentar la práctica de esta actividad. Así, decide emprender un estudio para conocer cuáles son los factores que más impactan en los accidentes viales que involucran ciclistas. Este conocimiento, además, podría ayudar a las autoridades y planificadores urbanos en la implementación de mecanismos que reduzcan la ocurrencia de accidentes, así como otros planes de movilidad sostenible. Para realizar este estudio BiciAlpes han recopilado datos, de fuentes abiertas de la Alcaldía, sobre accidentes en los cuales se han visto involucrados ciclistas.

BiciAlpes los ha contactado para realizar este proceso de caracterización e identificación de patrones que puedan ser utilizados para entender los factores que indicen en la severidad de los accidentes, con el fin de trazar mapas de seguridad vial para los ciclistas.  Los datos, al igual que el diccionario de datos, los encuentra disponibles en este directorio: [datos](./datos)

### Instrucciones 

Para el desarrollo del proyecto se sugiere aplicar la metodología ASUM-DM:

1. **Entendimiento de los datos:** en esta etapa es importante saber si los datos son o no suficientes para el alcance del proyecto y, en caso de serlo, entender bien sus características para poder definir el camino de limpieza y preparación para lograr el objetivo del proyecto.
En particular, deben incluir cuántos datos se tienen (filas y columnas) y los tipos de variables. Es importante realizar un perfilamiento completo   que incluya estadística descriptiva y gráficos sobre los datos, señalando sus principales estadísticos: media, varianza, desviación estándar, etc., para el caso de las columnas numéricas. En caso de datos categóricos recuerde que es importante conocer las categorías y en qué proporción se presentan. Tener en cuenta que una parte importante de esta etapa está relacionada con el análisis a nivel de calidad de datos y, en particular, a nivel de las dimensiones de calidad (completitud, unicidad, consistencia, validez) para identificar las actividades de preparación que requieren los datos.

2. **Preparación de datos:** es el procedimiento llevado a cabo para transformar los valores actuales de acuerdo con los algoritmos a utilizar y el objetivo de negocio a resolver. Incluye la limpieza de los datos, como el manejo de los datos nulos (missing values) y los valores atípicos (outliers).

3. **Modelamiento:** en este paso se lleva a cabo la elección del modelo con el que queremos cumplir nuestra tarea y su refinamiento.
En este caso, deben usar el algoritmo de K-Means y deberán compararlo con otros dos algoritmos como clustering jerárquico, DBScan, HDBScan, Gaussian Mixture.
Tengan en cuenta que, en ambientes profesionales, la elección y justificación del algoritmo y sus hiperparámetros hace parte de su tarea de consultoría.
Se sugiere explorar la generación de clústeres que puedan llevar a mejores valores de coeficiente de silueta, al igual que a mejor comprensión de los grupos por parte de la organización. En este punto recuerde incluir la descripción del algoritmo utilizado.

4. **Validación:** en modelos de aprendizaje no supervisado la validación de los modelos es un reto importante que deben asumir los consultores.
    
    4.1 **Validación cuantitativa:** la calidad desde el punto de vista cuantitativo puede validarse utilizando el coeficiente de silueta
y ser ajustado siguiendo guías como el método del codo. En caso de contar con datos anotados es posible también realizar una validación externa. Información adicional para complementar su interpretación puede encontrarla en este [enlace](https://towardsdatascience.com/k-means-clustering-algorithm-applications-evaluation-methods-and-drawbacks-aa03e644b48a). Esta métrica tiene sentido con el algoritmo de k-means. Revise lo apropiado según el algoritmo utilizado.
    
    4.2 **Validación cualitativa:** una vez realizada la validación cuantitativa, se debe hacer una descripción de los grupos obtenidos y relacionarlo con el objetivo que tenía el negocio para ver si es posible utilizar el resultado obtenido, o hay que seguir trabajando en alguna direccióne específica (clústers y conclusiones del proceso) para la comprensión por parte de la empresa.

5. **Visualización:** El estudiante debe proponer una visualización de los resultados obtenidos en un tablero de control,
de tal manera que el cliente tenga la capacidad de entender los resultados obtenidos en su labor de consultoría.

## <a name="entregables"></a> Entregables
- Informe que debe incluir:
    - Descripción detallada de cada etapa según las instrucciones dadas previamente
    - Incluir una descripción general de cómo funciona cada algoritmo utilizado y el nombre del estudiante que utilizó cada algoritmo.
    - Se espera que el informe no supere las 8 páginas.
- A nivel de visualización recuerde incluir el tablero de control construido (los archivos fuente y enlace para ejecutarlo)
- Presentación con los resultados
- Notebook ejecutado

    
Algunas preguntas que pueden guiar su desarrollo son: 

1. ¿Qué criterios son importantes para la selección del modelo? 

2. ¿Cómo medir la calidad del modelo construido? ¿Cómo saber que el modelo construido tiene una buena calidad?  

3. ¿Qué retos tienen estos modelos no supervisados, si se quisieran aplicar a nivel profesional?

4. ¿Cómo varía la calidad del modelo obtenido si aplicó diferentes algoritmos?

5. ¿Qué pasa en la ejecución de los algortimos si se incluyen variables categóricas nominales. ¿Qué tratamiento se les debe aplicar? 


**Nota:** 
Recuerde que la presentación debe estar orientada a la organización, por lo que se recomienda evitar el uso de términos muy técnicos y utilizar un lenguaje que sea familiar en el contexto de aplicación. Se les sugiere centrarse en la interpretación de los resultados.


## Instrucciones de Entrega
- El laboratorio se entrega en grupos de mínimo 2 y máximo 3 estudiantes. Estos estudiantes pueden ser de diferentes secciones.
- Recuerde hacer la entrega por la sección unificada en Bloque Neón, antes del domingo 19 de febrero a las 22:00.   
  Ese será el único medio por el cual se recibirán entregas.

## <a name="rubrica"></a> Rúbrica de Calificación

A continuación se encuentra la rúbrica de calificación.

**Nota:** Los siguientes porcentajes hacen referencia a la nota grupal, que corresponde a un 80% de la nota inidiviudal.  
El 20% restante se calcula según el puntaje obtenido en la implementación del algoritmo del cual el estudiante estuvo a cargo dentro del grupo.

| Concepto | Porcentaje |
|:---:|:---:|
| Descripción y análisis del entendimiento de los datos y de las tareas sugeridas de transformación | 15% |
| Descripción del preprocesamiento realizado, el genérico y el relacionado con el algoritmo utilizado. Justitificar utilizando el entendimiento de los datos | 10% |
| Implementación de K-means, descripción corta del algoritmo y de las de las decisiones más importantes asociadas a la implementación del algoritmo y los hiperparámetros configurados | 6% |
| Implementación de un segundo algoritmo, descripción corta del algoritmo y de las decisiones más importantes asociadas a la implementación del algoritmo y los hiperparámetros configurados | 10% |
| Implementación de un tercer algoritmo de libre elección, descripción corta del algoritmo y de las decisiones más importantes asociadas a la implementación del algoritmo y los hiperparametros configurados | 10% |
| Análisis de los resultados obtenidos y justificación del modelo recomendado para el caso propuesto | 24% |
| Presentación para BiciAlpes con resultados, recomendaciones dadas a la empresa y visualización usando el tablero de control construido| 20% |
| Notebook asociado, ejecutado | 5% |

## <a name="sugerencias"></a> Sugerencias y aclaraciones

 - Nota 1: la interpretación de los clusters se debe hacer en términos de las variables que considere importantes (incluya las usadas para la construcción de los clusters
 pero también otras variables, en especial las categóricas que no hayan incluido)
 - Nota 2: Analizar si los valores de cada columna corresponden a valores adecuados para el negocio, en caso de que no lo sean, deben tratar dichos valores y justificar sus decisiones.

Los siguientes enlaces pueden serle de utilidad para la implementación en Python. 

* [Ejemplo de K-Means usando Sklearn](https://jakevdp.github.io/PythonDataScienceHandbook/05.11-k-means.html)

* [Artículo de Towards Data Science: K-means with Sklearn](https://towardsdatascience.com/k-means-clustering-with-scikit-learn-6b47a369a83c)

* [Artículo de Towards Data Science: Introducción al análisis de datos con Python](https://towardsdatascience.com/tips-and-tricks-for-fast-data-analysis-in-python-f108ad32fa90) 

 - Cada integrante del grupo debe estar encargado de la implementación de un algoritmo distinto. Sin embargo, todos los integrantes del grupo
deben tener la capacidad de explicar lo realizado por los demás compañeros
 - El análisis de resultados y su justificación debe ser realizado en grupo.
 - Las notas de los integrantes dentro de un mismo grupo de laboratorio pueden variar ya que cada integrante está encargado de la implementación de un algoritmo distinto. 
