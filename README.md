# Pipeline de ML
## 
Se van a utilizar los datos de la competencia de kaggle "House Prices - Advanced Regression Techniques https://www.kaggle.com/c/house-prices-advanced-regression-techniques/overview
Competition Description
![housesbanner](https://user-images.githubusercontent.com/2281529/134782394-25da2570-550b-4b7a-85fe-219630455631.png)
Ask a home buyer to describe their dream house, and they probably won't begin with the height of the basement ceiling or the proximity to an east-west railroad. But this playground competition's dataset proves that much more influences price negotiations than the number of bedrooms or a white-picket fence.

With 79 explanatory variables describing (almost) every aspect of residential homes in Ames, Iowa, this competition challenges you to predict the final price of each home.

## Activades
Para la reproducción del PIPELINE se generaron dos COLAB, si bien no se pueden reproducir los procesos de automatización, scheduling, etc. de un PIPELINE productivo. se trató de seguir un ciclo de vida de ML orquestado similar a un ambiente productivo  
El primer COLAB abarca las Etapas de Ingesta/Visualización/EDA/Modelado ML 
colab https://github.com/gusper01/seminarioITBA/blob/gh-pages/seminarioITBA_EDA.ipynb
Y el segundo COLAB las Etapas de Persistencia/Recuperación de Datos
colab https://github.com/gusper01/seminarioITBA/blob/gh-pages/seminarioITBA_PIPELINE.ipynb

Clonado del Repositorio
git clone https://github.com/gusper01/seminarioITBA.git

## Etapas del PipeLine 🚀
Para este Pipeline se definieron las siguientes etapas  
### Ingesta de Datos 📋
Se toman los datasets de la competencia de Kaggle  
### Análisis Exploratorio (EDA) 🔧
Se realiza visualizaciones de los datasetas de entrenamiento y test
### Limpieza de Datos ⚙️
Se identifican features y se realizan actividades de limpieza e imputación de datos
### Label Enconding/Baseline 🔩
Se realizan encoding de features a los efectos de poder utilizar algoritmo XGBoost
Se genera una función de Baseline para comparar feature importance ,
### Feature Engineering  ⌨️
Se crean nuevas posibles Features y se comparan con baseline
### Creación del Modelo 📦
Se genera modelo y predicciones 
Se utilizará solo el algoritmo XGBoost por limitaciones de tiempo. Se generá el archivo con la predicción para hacer el submit a Kaggle y un archivo de de salida para realizar persistencia "datatotal01102021.csv" y continuar con el PIPELINE de ML (en otro COLAB)


### Persistencia 🔩
#### Configuración SPARK en COLAB
_Una serie de ejemplos paso a paso que te dice lo que debes ejecutar para tener un entorno de desarrollo ejecutandose_
_Explica que verifican estas pruebas y por qué_
#### Creación Dataframe Spark con datos de predicción 
Se genera Dataset Spark y se realizan visualizaciones de datos y schema
Se realizan "casteos" de columnas de Dataset Spark
#### Persistencia
Se genera persistencia grabando un archivo parquet
A partir de archivo parquet se realizan consultas PYSPARK SQL y se genera un filtrado de datos en base a un condicion se exporta esta salida a un Pandas Dataframe
#### Visualización

####```
Da un ejemplo
```

_Dí cómo será ese paso_


_Que cosas necesitas para instalar el software y como instalarlas_

```
Da un ejemplo
```
```
Da un ejemplo
```

_Y repite_

```
hasta finalizar
```
_Finaliza con un ejemplo de cómo obtener datos del sistema o como usarlos para una pequeña demo_


_Explica que verifican estas pruebas y por qué_

```
Da un ejemplo
```

_Agrega notas adicionales sobre como hacer deploy_

## Construido con 🛠️

_Menciona las herramientas que utilizaste para crear tu proyecto_

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

* **Gustavo Pereyra** - [gusper01](https://github.com/gusper01)

También puedes mirar la lista de todos los [contribuyentes](https://github.com/your/project/contributors) quíenes han participado en este proyecto. 

## Licencia 📄

Este proyecto está bajo la Licencia (Tu Licencia) - mira el archivo [LICENSE.md](LICENSE.md) para detalles

## Expresiones de Gratitud 🎁

* Comenta a otros sobre este proyecto 📢
* Invita una cerveza 🍺 o un café ☕ a alguien del equipo. 
* Da las gracias públicamente 🤓.
* etc.



---
⌨️ con ❤️ por [Villanuevand](https://github.com/Villanuevand) 😊
