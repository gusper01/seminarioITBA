# Pipeline de ML
## 
Se van a utilizar los datos de la competencia de kaggle "House Prices - Advanced Regression Techniques https://www.kaggle.com/c/house-prices-advanced-regression-techniques/overview
Competition Description
![housesbanner](https://user-images.githubusercontent.com/2281529/134782394-25da2570-550b-4b7a-85fe-219630455631.png)
Ask a home buyer to describe their dream house, and they probably won't begin with the height of the basement ceiling or the proximity to an east-west railroad. But this playground competition's dataset proves that much more influences price negotiations than the number of bedrooms or a white-picket fence.

With 79 explanatory variables describing (almost) every aspect of residential homes in Ames, Iowa, this competition challenges you to predict the final price of each home.

## Actividades
Para la reproducción del PIPELINE se generaron dos COLAB, si bien no se pueden reproducir los procesos de automatización, scheduling, etc. de un PIPELINE productivo. se trató de seguir un ciclo de vida de ML orquestado similar a un ambiente productivo  
El primer COLAB abarca las Etapas de Ingesta/Visualización/EDA/Modelado ML 
colab https://github.com/gusper01/seminarioITBA/blob/gh-pages/seminarioITBA_EDA.ipynb
Y el segundo COLAB las Etapas de Persistencia/Recuperación de Datos
colab https://github.com/gusper01/seminarioITBA/blob/gh-pages/seminarioITBA_PIPELINE.ipynb

Repositorio
git clone https://github.com/gusper01/seminarioITBA.git

## Etapas del PipeLine 🚀
```
Se definieron las siguientes etapas  
```
### Ingesta de Datos 📋
```
Se toman los datasets de la competencia de Kaggle  
```
### Análisis Exploratorio (EDA) 🔧
```
Se realizan visualizaciones de los datasets de entrenamiento y test
```
### Limpieza de Datos ⚙️
```
Se identifican features y se realizan actividades de limpieza e imputación de datos
```
### Label Enconding/Baseline 🔩
```
Se realizan encoding de features a los efectos de poder utilizar algoritmo XGBoost
Se genera una función de Baseline para comparar feature importance y a los efectos de medir los modelos que se vayan desarrollando y una funcion de scoring con RMSLE (Root Mean Squared Log Error) es lo pedido en la competencia de kaggle original y es usual como métrica en problemas de regresión)
```

### Feature Engineering  ⌨️
```
Se crean nuevas posibles Features y se comparan con baseline
Se va a utilizar la métrica de Informacion Mutua. Esta tecnica se parece mucho a la correlación en el sentido de que mide la relación entre dos cantidades. La ventaja de la información mutua es que puede detectar cualquier tipo de relación, mientras que la correlación solo detecta relaciones lineales. Es fácil de usar e interpretar, resistente al overfitting y capaz de detectar cualquier tipo de relación. Intuitivamente, la información mutua media mide la información que X e Y comparten: mide en cuánto el conocimiento de una variable reduce nuestra incertidumbre sobre la otra. Por ejemplo, si X e Y son independientes, entonces conocer X no da información sobre Y y viceversa, por lo que su información mutua es cero. En el otro extremo, si X e Y son idénticas entonces toda información proporcionada por X es compartida por Y: saber X determina el valor de Y y viceversa. Por ello, la información mutua media es igual a la información contenida en Y (o X) por sí sola, también llamada la entropía de Y (o X: claramente si X e Y son idénticas tienen idéntica entropía https://es.m.wikipedia.org/wiki/Informaci%C3%B3n_mutua
```
### Hyperparameter Tuning  🛠️
```
A los fines del TP esta actividad no se realizó de forma práctica pero debería estar en un ciclo de pipeline productivo ya que es clave sobre todo en los algoritmos como XGBoost. Se puede implementar con una función que optimice los parámetros. Los parámetros se refieren entre otras características a: Cantidad de Hojas, Produndidad, iteracciones, tipo de validacion, escalamiento, Se puede utilizar optimizacion bayesiana para hacer la búsqueda de los mejores parametros. En esta caso que se utiliza XGBOOST con PYTHON se puede utilizar HYPEROT, también se puede probar manualmente. Los algoritmos de boosting se procesan de forma secuencial para la generacion de cada arbol y en gral. requieren mucho hardaware comprometido y muchas veces es conveniente realizarlo utilizando un servicio en la nube
```
### Creación del Modelo 📦
```
Se genera modelo y predicciones 
Se utilizará solo el algoritmo XGBoost por limitaciones de tiempo. Se generá el archivo con la predicción para hacer el submit a Kaggle y un archivo de de salida para realizar persistencia "datatotal01102021.csv" y continuar con el PIPELINE de ML (en otro COLAB)
```
### Persistencia 🔩
```
Se configura SPARK en Colab
Creación Dataframe Spark con datos de predicción
Se genera Dataset Spark y se realizan visualizaciones de datos y schema
Se realizan "casteos" de columnas de Dataset Spark
Se genera persistencia grabando un archivo parquet
A partir de archivo parquet se realizan consultas PYSPARK SQL y se genera un filtrado de datos en base a un condicion se exporta esta salida a un Pandas Dataframe
```
#### Recuperación de Datos 🔩
```
Se visualiza extraccion de datos de archivo Parquet
```

## Construido con 🛠️

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - El framework web usado
* [Maven](https://maven.apache.org/) - Manejador de dependencias
* [ROME](https://rometools.github.io/rome/) - Usado para generar RSS

## Contribuyendo 🖇️

Por favor lee el [CONTRIBUTING.md](https://gist.github.com/villanuevand/xxxxxx) para detalles de nuestro código de conducta, y el proceso para enviarnos pull requests.

## Wiki 📖

Puedes encontrar mucho más de cómo utilizar este proyecto en nuestra [Wiki](https://github.com/tu/proyecto/wiki)

## Versionado 📌

Usamos [SemVer](http://semver.org/) para el versionado. Para todas las versiones disponibles, mira los [tags en este repositorio](https://github.com/tu/proyecto/tags).

## Autor ✒️

* **Gustavo Pereyra** - [gusper01](https://github.com/gusper01)😊

## Licencia 📄

Este proyecto está bajo la Licencia (Tu Licencia) - mira el archivo [LICENSE.md](LICENSE.md) para detalles

## Expresiones de Gratitud 🎁

* Comenta a otros sobre este proyecto 📢
* Invita una cerveza 🍺 o un café ☕ a alguien del equipo. 
* Da las gracias públicamente 🤓.
* etc.



---
⌨️ con ❤️ por [Villanuevand](https://github.com/Villanuevand) 😊
