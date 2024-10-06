# README.md

## Del Codón al Clúster: Agrupamiento y Clasificación de Secuencias de Proteínas

- **Laura Lasso García**
- **Andrea Mayor Gómez**

### Descripción

Este código realiza la clasificación de secuencias de proteínas utilizando técnicas de agrupamiento no supervisado y modelos de clasificación supervisada. El código aborda el problema de clasificación de proteínas basado en sus secuencias, utilizando técnicas de aprendizaje automático como *K-Means clustering* para agrupar las secuencias y clasificadores supervisados como *Random Forest* y *SVM* para entrenar y evaluar los datos etiquetados.

El flujo general del código es el siguiente:
1. **Lectura de secuencias de proteínas:** Se cargan secuencias de archivos en formato FASTA.
2. **One-Hot Encoding:** Se codifican las secuencias de aminoácidos en un formato numérico adecuado para modelos de machine learning.
3. **K-Means clustering:** Se agrupan las secuencias en clústeres utilizando K-Means.
4. **Visualización PCA:** Reducción de la dimensionalidad para visualizar los clusters en un espacio de 2D.
5. **Clasificación supervisada:** Se entrenan modelos de *Random Forest* y *SVM* para clasificar las secuencias con base en las etiquetas generadas por K-Means y se evalúan las predicciones.

### Tecnologías Usadas

1. **NumPy:** Se utilizó para manejar estructuras de datos numéricas y realizar el One-Hot Encoding de las secuencias de proteínas de manera eficiente.
2. **Pandas:** Para manipular y visualizar datos tabulares, como la asociación de las secuencias de proteínas con las etiquetas de clusters.
3. **scikit-learn (K-Means, PCA, RandomForestClassifier, SVM):** Se emplearon varias herramientas de la librería de aprendizaje automático:
   - *KMeans* para agrupar secuencias no etiquetadas.
   - *PCA* para reducir la dimensionalidad y facilitar la visualización.
   - *RandomForestClassifier* y *SVC* (SVM) para clasificar las secuencias utilizando los datos etiquetados.
4. **Matplotlib:** Para la visualización gráfica de los clusters en el espacio PCA.
5. **Tabulate:** Para mostrar de manera ordenada los resultados de los reportes de clasificación en formato de tabla.
6. **Biopython (SeqIO):** Aunque no se menciona explícitamente en el código, sería necesario para la carga y el manejo de las secuencias de archivos FASTA.

Estas tecnologías fueron seleccionadas por su facilidad de uso y eficiencia en tareas como manipulación de datos, procesamiento de secuencias biológicas, y algoritmos de aprendizaje automático.

### Razonamiento

El enfoque implementado es adecuado por varias razones:

1. **Agrupamiento no supervisado con K-Means:** Permite agrupar secuencias de proteínas sin necesidad de etiquetas predefinidas, lo que es ideal para analizar conjuntos de datos en los que no se dispone de información previa sobre las clases. K-Means es eficiente para este tipo de datos de alta dimensionalidad.
   
2. **Codificación One-Hot:** Este método de codificación es adecuado para representar secuencias de proteínas, ya que transforma cada aminoácido en un formato binario que los algoritmos de aprendizaje automático pueden interpretar fácilmente.

3. **Reducción de dimensionalidad con PCA:** Debido a la alta dimensionalidad de los datos (una secuencia de aminoácidos codificada ocupa mucho espacio), es necesario reducir la dimensionalidad para visualizar y analizar los clusters de manera comprensible.

4. **Modelos supervisados (Random Forest y SVM):** Después de generar etiquetas con K-Means, se utilizan estos modelos supervisados para clasificar y evaluar las secuencias. Random Forest es robusto y manejable para datos grandes y diversos, mientras que SVM es conocido por su precisión en problemas de clasificación.
