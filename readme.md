# Clasificación de Malaria en Células: Estudio Comparativo de Transfer Learning

## Ruta Elegida y Dataset

**Ruta Seleccionada**: Clasificación con modelos pre-entrenados (Transfer Learning)

**Dataset**: Cell Images for Detecting Malaria
- **Fuente**: [Kaggle - Cell Images for Detecting Malaria](https://www.kaggle.com/datasets/iarunava/cell-images-for-detecting-malaria)
- **Fuente Original**: [National Library of Medicine (NIH)](https://lhncbc.nlm.nih.gov/LHC-research/LHC-projects/image-processing/malaria-datasheet.html)
- **Licencia**: Dominio público (NIH/NLM - National Institutes of Health/National Library of Medicine)
- **Descripción**: 27,558 imágenes microscópicas de células sanguíneas clasificadas como "Parasitized" (infectadas) y "Uninfected" (no infectadas)



## Cómo Ejecutar

1. **Abrir el notebook**: En la carpeta notebooks se encuentra el archivo `Proyecto_Clasificacion.ipynb` que puede ser abierto en Google Colab o Jupyter Notebook
2. **Configurar GPU**: En Google Colab, ir a `Runtime → Change runtime type → GPU`
3. **Configurar la ruta del proyecto**: En la primera celda de la Sección 2 del notebook, define la ruta del directorio principal. La carpeta `results` debe estar ubicada dentro de esta misma ruta.
4. **Ejecutar celdas**: Ejecutar las celdas en orden secuencial

### Ejecución Rápida (Solo Evaluación)
Si desea **únicamente visualizar las métricas** sin entrenar:
- Ejecutar directamente la **última celda** del notebook, en esa celda podrás establecer la ruta del proyecto en la  variable `PROJECT_ROOT`.
- Esta celda carga los modelos pre-entrenados (`.pth`) desde la carpeta `results`
- Muestra automáticamente las métricas y gráficos comparativos

## Cómo Entrenar

Para entrenar los modelos desde cero:

1. **Ejecutar secciones 1-3**: Preparación de datos y configuración
2. **Sección 4 - Entrenamiento**: Contiene 3 subsecciones, una para cada modelo:
   - Subsección 4.1: Entrenamiento VGG16
   - Subsección 4.2: Entrenamiento ResNet50
   - Subsección 4.3: Entrenamiento EfficientNetB0
3. **Guardar modelos**: Los modelos entrenados se guardan automáticamente como archivos `.h5` en la carpeta `results`


## Cómo Generar la tabla y el gráfico de métricas.

### Opción 1: Flujo Completo
Ejecutar todas las celdas en orden (secciones 1-5)


### Opción 2: Solo Evaluación
1. Ir directamente a la **última celda** del notebook
2. Cambia el valor de la variable PROJECT_ROOT por la ruta del directorio donde se encuentra la carpeta principal de tu proyecto. Asegúrate de que la carpeta results esté ubicada dentro de esa misma ruta.
3. Ejecutar para cargar modelos pre-entrenados desde Google Drive
4. Se generan automáticamente:
   - Tabla comparativa de métricas (CSV)
   - Gráficos de barras por métrica

## Archivos
En la carpeta `results` se encuentran todos los archivos generados durante el entrenamiento y evaluación de los modelos. A continuación, se listan los principales:
1. model_vgg16.h5, model_resnet50.h5 y model_efficientnet.h5. Son los respaldos de los modelos entrenados con sus pesos para poder ser usados en google collab para visualizar rápidamente sus métricas sin tener que entrenarlos de nuevo.
2. metrics_comparison(train vs test).csv: Tabla comparativa de las métricas del modelo.
3. metrics_comparison(train vs test).png: Gráfico de barras para visualizar las métricas por modelo.
4. sample_predictions.png: Predicciones realizadas por los modelos.
5. confusion_matrices.png: Matriz de confusión.