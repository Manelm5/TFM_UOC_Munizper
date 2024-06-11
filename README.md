# TFM-UOC_Munizper: Refinamiento de modelos de IA para la identificación de cáncer de piel

La optimización de modelos de IA puede reducir errores y aumentar la confiabilidad en la identificación de lesiones cutáneas sospechosas, lo que mejora la atención médica y la calidad de vida de los pacientes facilitando también el acceso a la atención médica especializada en áreas remotas o con escasez de recursos, ampliando así el alcance y el impacto de la detección precoz. 

Se realiza una continuación directa de trabajos anteriormente realizados para investigar una mejora de resultados de predicción de tumores malignos en imágenes dermatológicas. Esta mejora se busca no solo a través de la optimización de algoritmos y técnicas de aprendizaje automático, sino también integrando factores externos relevantes, como la inclusión de condiciones ambientales que podrían influir en el desarrollo y la detección de tumores. 

Con miras al perfeccionamiento de los modelos, se busca abordar diversas tipologías de imágenes dermatológicas, tanto de acceso público como privado, gracias a la colaboración establecida con el Dr. José J. Pereyra Rodríguez del Hospital Universitario Virgen del Rocío de Sevilla. Además, se contempla la integración de datasets públicos que suministren datos relativos a los factores externos que puedan incidir en el análisis, enriqueciendo así la comprensión y capacidad predictiva del sistema.

Este trabajo tiene como objetivo principal investigar cómo influyen los factores externos en la herramienta de diagnóstico temprano para ayudar en la detección de un posible cáncer de piel.

# Ejecución del proyecto

## Pre-requisitos

Librerías:
```
numpy 
pandas 
os
cv2
sys
timeit
matplotlib
seaborn 
datasets
warnings
csv
random
sklearen
imblearn
tensorflow
vit_keras
tensorflow_addons
image
Pillow
```
La versión utilizada de Tensorflow es 2.10.1, de Cuda 64_112 y de Cudnn 64_9.

## Directorios

Organización de carpetas:
- Código:
  - Carpeta dataset inicial (HAM10000, HIBA, MSKCC, Sevilla)
    - x_solar_calcs.csv
    - x_metadata.csv
    - final_metadata_x.csv
  - Datos
    - CF2
      - imágenes
        - BENIGNO
        - MALIGNO
      - salidas
    - metadata_CF2.csv
    - external_factors_metadata_CF2.csv
  - TFM_Clima_Data_x.ipynb
  - TFM_Exploratory_x.ipynb
  - TFM_Data_Preparation.ipynb
  - TFM_Models_Training.ipynb

**x_solar_calcs**: Metadatos externos climatológicos de un dataset inicial.

**x_metadata**: Metadatos generales de un dataset inicial.

**final_metadata_x.csv**: Dataset que será utilizado como input para la generación del dataset de metadatos final.

**imágenes**: Carpeta en la cual se encuentras dos subcarpetas con las imágenes a tratar.

**salidas**: Carpeta donde se almacenan los archivos del dataset .npy, los pesos de los modelos, los historiales de los entrenamientos y la matriz de pesos.

**metadata_CF2.csv**: Dataset de las imágenes una vez han sido tratadas.

**external_factors_metadata_CF2.csv**: Dataset de factores externos una vez ha sido tratado.

**TFM_Clima_Data_x.ipynb**: Código fuente utilizado para generar los datos climáticos que serán adheridos a un dataset inicial.

**TFM_Exploratory_x.ipynb**: Código fuente utilizado para realizar el análisis exploratorio de un dataset inicial.

**TFM_Data_Preparation.ipynb**: Código fuente que procesa las imágenes y prepara el dataset de metadatos final combinando los datasets iniciales seleccionados.

**TFM_Models_Training.ipynb**: Código fuente que entrena los diferentes modelos con los datos generados.

## Preparacion de los datos

Por defecto, este trabajo ha sido realizado con los datasets de HAM10000, HIBA, MSKCC y el Hospital Universitario Virgen del Rocío de Sevilla.

1. Almacenar las imágenes a tratar en la carpeta BENIGNO o MALIGNO en función de su clase.
2. Recoger datos climatológicos a utilizar
3. Modificar TFM_Clima_Data_x.ipynb para generar un subset de factores climatológicos.
5. Generar metadatos pertenecientes a cada uno de los datasets iniciales mediante TFM_Exploratory_x.ipynb
6. Modificar TFM_Data_Preparation.ipynb para generar los archivos .npy que serán utilizados para el entrenamiento.

 ## Entrenamiento

 Seleccionar en TFM_Models_Training.ipynb mediante 'True' o 'False' los modelos que se desea que sean entrenados.
 Por defecto el número de parámetros para el dataset de metadatos está a '3'.

 ## Autores
 
 * **Manuel Muñiz Perálvarez**
> Idea original de David Martín Tinaquero

> Continuación de Enrique Fernández Morales

## Licencia

Este proyecto se encuentra bajo la licencia CC0-1.0. Para más información revisa el archivo LICENSE.md del repositorio.
