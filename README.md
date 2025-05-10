# Análisis RFM de Cobros Aprobados de Comercios

Este proyecto realiza un análisis de **RFM** (Recencia, Frecuencia, Monto) para segmentar a los comercios en función de sus **cobros aprobados**. Utilizando el algoritmo de **K-Means**, se identificaron diferentes grupos de comercios con comportamientos similares en términos de su historial de cobros. 
## Objetivo del Análisis

El análisis RFM se utilizó para evaluar los comportamientos de los comercios que realizaron cobros aprobados. Las tres variables principales que componen el análisis son:
- **Recencia (R):** Cuántos días han pasado desde el último cobro aprobado.
- **Frecuencia (F):** Cuántos cobros aprobados ha realizado el comercio en un período determinado.
- **Monto (M):** El total de dinero generado por los cobros aprobados (en dólares).

## Metodología

1. **Preprocesamiento de Datos:**
   - Se cargaron los datos de cobros aprobados y se prepararon para el análisis RFM.
   - Las variables RFM fueron calculadas y estandarizadas para asegurar que el modelo de clustering no se viera afectado por la escala de las variables.

2. **Modelado de Clustering con K-Means:**
   - Se aplicó el algoritmo de **K-Means** para segmentar a los comercios en diferentes grupos (clústeres) según sus características RFM.
   - Se utilizaron métricas de validación como la **silhouette score**, **calinski-harabasz** y **davies-bouldin** para evaluar el rendimiento del modelo y seleccionar el número óptimo de clústeres.

3. **Interpretación de los Clústeres:**
   - Se obtuvieron 4 clústeres que representan diferentes tipos de comercios según su comportamiento en relación con los cobros aprobados.
   - Cada clúster fue analizado en términos de su **gasto promedio (monto)**, **frecuencia de cobros** y **recencia**.

## Descripción de los Clústeres

| **Cluster** | **Gasto Promedio (USD)** | **Frecuencia de Cobros** | **Recencia Promedio (días)** | **Interpretación** |
|-------------|--------------------------|---------------------------|------------------------------|---------------------|
| **0**       | 23.98                    | 5.71                      | 414.39                       | Comercios que gastan más dinero y tienen buena frecuencia de cobros, pero cuya última transacción fue hace un tiempo. Podrían ser comercios a reactivar. |
| **1**       | 5.68                     | 2.17                      | 318.66                       | Comercios de bajo gasto y baja frecuencia de cobros. Su recencia es moderada, pero tienen un comportamiento de compra más esporádico. |
| **2**       | 12.85                    | 3.95                      | 395.51                       | Comercios con un gasto moderado y una frecuencia aceptable de cobros. La recencia es alta, indicando que no han realizado cobros recientemente. |
| **3**       | 7.06                     | 2.21                      | 488.03                       | Comercios con bajo gasto y baja frecuencia de cobros, además de una recencia muy alta, lo que indica que no han realizado cobros en mucho tiempo. |

## Conclusiones 
Los clústeres 0 y 2 parecen representar a los clientes de mayor valor o más activos, aunque en el caso de 0 presenta una alta recencia.

Los clústeres 1 y 3 representan clientes menos comprometidos, con una menor frecuencia de compra y un gasto reducido. El clúster 3 tiene una recencia aún más alta, lo que indica que estos clientes están bastante inactivos.


## Herramientas y Tecnologías Utilizadas

- **Python:** Para la implementación del análisis y procesamiento de datos.
- **Bibliotecas:** Pandas, Scikit-learn, Matplotlib, entre otras.
- **K-Means Clustering:** Para segmentación de comercios en grupos basados en su comportamiento de cobros.
- **Métricas de Evaluación:** Silhouette Score, Calinski-Harabasz y Davies-Bouldin.


