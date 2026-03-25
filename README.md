![Banner](Banner.png)
##  **¿En qué consiste el proyecto?**

Este proyecto consiste en un sistema de **Visión Computacional** que automatiza el análisis dermatológico mediante **Redes Neuronales Convolucionales (CNN)** para identificar anomalías cutáneas. A través del entrenamiento de modelos de **Aprendizaje Profundo (Deep Learning)**, se busca crear una herramienta que funcione como un asistente de diagnóstico preciso. Con el fin de proporcionar una etiqueta diagnóstica preliminar que sirva de apoyo a los profesionales de la salud, permitiendo que la tecnología traduzca patrones visuales complejos en información clínica accionable y confiable. 

Por consiguiente ayuda a reducir la carga operativa de los hospitales y mejorar la precisión del diagnóstico inicial, econvirtiendose en una herramienta esencial para modernizar la atención médica preventiva a nivel global.



# **La Ciencia Detrás del Proyecto: Fundamentos Teóricos y Contexto**

---
## 1. El Problema Clínico: Diagnóstico Visual en Dermatología
### Abordaje tradicional del diagnóstico dermatológico
<p >
   Previo al desarrollo de este proyecto, el diagnóstico de enfermedades cutáneas se fundamentaba en un proceso clínico que combinaba la inspección visual directa, la evaluación de criterios clínicos estandarizados y, en casos de sospecha, el análisis histopatológico mediante biopsia. Los especialistas realizaban la evaluación de lesiones cutáneas utilizando dermatoscopios, dispositivos de aumento que permiten visualizar estructuras subepidérmicas no apreciables a simple vista, aplicando sistemas de clasificación como el criterio ABCD (Asimetría, Bordes, Color, Diámetro) para la identificación de melanomas.
</p>
<div align="center">
  <img src="https://github.com/nelsondonado/Ciencia-de-datos/blob/main/lesion.jpg" width="35%"/>
  &nbsp;
  <img src="https://github.com/nelsondonado/Ciencia-de-datos/blob/main/lesion_dermatoscopio.jpeg" width="35%"/>
</div>

### Limitaciones del enfoque tradicional
<p>
   El abordaje tradicional presentaba múltiples limitaciones que este proyecto busca atender. En primer lugar, la subjetividad inherente al diagnóstico visual generaba variabilidad inter-observador significativa, con estudios que reportan concordancias entre dermatólogos tan bajas como el 60-70% para lesiones pigmentadas. En segundo lugar, la precisión diagnóstica dependía fuertemente de la experiencia clínica del especialista, existiendo diferencias sustanciales entre dermatólogos generales y subespecialistas en dermatoscopia oncológica.

([Aqui se puede insertar un gráfico o diagrama que ilustre la variabilidad inter-observador en el diagnóstico dermatológico, mostrando cómo diferentes especialistas pueden clasificar la misma lesión de manera distinta])

En tercer lugar, las barreras de acceso a atención especializada constituían un problema estructural. En regiones apartadas o países en desarrollo, la densidad de dermatólogos era insuficiente para atender la demanda poblacional, generando retrasos en la derivación y el diagnóstico. Finalmente, el diagnóstico tardío representaba la consecuencia más grave de estas limitaciones: mientras que el melanoma detectado en etapas tempranas (espesor <1mm) alcanza tasas de supervivencia superiores al 95% a cinco años, su detección en etapas avanzadas reduce esta cifra por debajo del 20%.

([Aqui se puede insertar una infografía que compare las tasas de supervivencia del melanoma según el estadio de detección, evidenciando la importancia crítica del diagnóstico temprano])
</p>


---
## 2. Fundamentos Técnicos: Visión por Computadora y Aprendizaje Profundo
### Redes Neuronales Convolucionales (CNN)
<p>
   El sistema desarrollado por los investigadores se fundamenta en Redes Neuronales Convolucionales, una clase de modelos de aprendizaje profundo inspirados en la organización del córtex visual de los mamíferos. Estas arquitecturas están diseñadas específicamente para procesar datos con estructura de cuadrícula, como las imágenes dermatológicas.

([Aqui se puede insertar un diagrama esquemático de la arquitectura de una Red Neuronal Convolucional, mostrando las capas de entrada, capas convolucionales, capas de pooling y capas completamente conectadas])

Las CNN operan a través de tres componentes fundamentales. Las capas convolucionales aplican filtros que se deslizan sobre la imagen para detectar patrones espaciales: en las primeras capas se identifican características de bajo nivel como bordes, texturas y colores; en capas más profundas, estas características se combinan para detectar estructuras de alto nivel como redes pigmentarias, puntos y glóbulos característicos de distintas condiciones dermatológicas.

([Aqui se puede insertar una visualización de las activaciones de una CNN, mostrando cómo las primeras capas detectan bordes y texturas simples mientras que las capas más profundas detectan estructuras complejas como redes pigmentarias])

Las capas de pooling reducen la dimensionalidad espacial, disminuyendo la carga computacional y otorgando invarianza traslacional. Finalmente, las capas completamente conectadas integran las características aprendidas para realizar la clasificación final mediante combinaciones no lineales.
</p>

### Transfer Learning: Fundamentos y aplicación
<p>
   El entrenamiento de una CNN desde cero requiere conjuntos de datos masivos, recursos computacionales extensos y presenta alto riesgo de sobreajuste cuando los datos son limitados. Ante esta realidad, los investigadores implementaron la estrategia de transfer learning, que consiste en aprovechar redes neuronales previamente entrenadas en conjuntos masivos como ImageNet (14 millones de imágenes, 1000 categorías) para transferir el conocimiento adquirido hacia el dominio dermatológico.

([Aqui se puede insertar un diagrama conceptual del proceso de Transfer Learning, mostrando cómo una red entrenada en ImageNet se adapta al dominio dermatológico mediante fine-tuning])

Esta estrategia se implementó mediante dos fases. En la primera fase, denominada feature extraction, se congelaron las capas convolucionales pre-entrenadas y se entrenaron únicamente las capas clasificadoras añadidas. En la segunda fase, conocida como fine-tuning, se descongelaron selectivamente algunas de las últimas capas convolucionales para reentrenarlas con tasas de aprendizaje reducidas, permitiendo que la red ajuste sus detectores de características para capturar patrones específicamente dermatológicos.
</p>

### Aumento de datos como estrategia de regularización
<p>
   Dada la limitación inherente de los datasets médicos, los investigadores implementaron técnicas de aumento de datos para maximizar la diversidad del conjunto de entrenamiento. Mediante transformaciones que incluyen rotaciones, reflejos horizontales y verticales, desplazamientos, ajustes de brillo y contraste, y distorsiones elásticas, cada imagen de entrenamiento se presenta al modelo con variaciones sintéticas en cada época, exponiéndolo a una diversidad mayor que la disponible originalmente y reduciendo el riesgo de sobreajuste.

([Aqui se puede insertar una imagen compuesta que muestre múltiples variaciones aumentadas de una misma lesión dermatológica original: rotación, reflejo, ajuste de brillo, distorsión elástica, etc.])
</p>

---
## 3. Métricas de Evaluación en Contexto Clínico
<p>
   La evaluación del sistema desarrollado no se limitó a métricas generalistas como la precisión global, sino que se orientó hacia indicadores con significado clínico específico, reconociendo que las consecuencias de los errores diagnósticos no son simétricas.
</p>
   
   #### - Sensibilidad (Recall):
   <p>
      Definida como la proporción de verdaderos positivos sobre el total de casos positivos reales. Esta métrica adquiere prioridad crítica para lesiones malignas como el melanoma, donde un falso negativo (no detectar una lesión maligna) puede tener consecuencias fatales para el paciente.
      </p>
   
   #### - Especificidad:
   <p>
       Definida como la proporción de verdaderos negativos sobre el total de casos negativos reales. Su relevancia radica en evitar procedimientos invasivos innecesarios (biopsias) y reducir la ansiedad generada por falsas alarmas.
       ([Aqui se puede insertar un diagrama que explique visualmente los conceptos de verdaderos positivos, falsos positivos, verdaderos negativos y falsos negativos utilizando una matriz de confusión])
       </p>

   #### - Área bajo la curva ROC (AUC-ROC):
   <p>
        Esta métrica evalúa el poder discriminatorio del modelo independientemente del umbral de decisión seleccionado, proporcionando una medida integral de su capacidad para distinguir entre clases.
     ([Aqui se puede insertar una gráfica que muestre una curva ROC típica, resaltando el área bajo la curva y explicando su interpretación])
     </p>

 
   #### - Valor Predictivo Negativo (VPN):
   <p>
      Definido como la proporción de verdaderos negativos sobre el total de negativos clasificados por el modelo. Esta métrica resulta particularmente relevante para un sistema de triaje, pues indica la confianza que puede depositarse cuando el modelo clasifica una lesión como benigna.
      El sistema desarrollado no pretende reemplazar al dermatólogo, sino constituirse como una herramienta de apoyo diagnóstico que permita priorizar casos sospechosos, reducir la carga cognitiva del especialista y acelerar la derivación de lesiones que requieren atención inmediata.
      ([Aqui se puede insertar un diagrama de flujo que ilustre el flujo de trabajo propuesto: desde la captura de imagen, pasando por el sistema de triaje basado en CNN, hasta la derivación a especialista según el nivel de sospecha])
      </p>

### Referencias (son las del punto 2, la idea es ponerlas al final del repositorio):
<p>
   Esteva, A., Kuprel, B., Novoa, R. A., Ko, J., Swetter, S. M., Blau, H. M., & Thrun, S. (2017). Dermatologist-level classification of skin cancer with deep neural networks. Nature, 542(7639), 115-118.

Haenssle, H. A., Fink, C., Schneiderbauer, R., Toberer, F., Buhl, T., Blum, A., ... & Uhlmann, L. (2018). Man against machine: diagnostic performance of a deep learning convolutional neural network for dermal melanoma recognition in comparison to 58 dermatologists. Annals of Oncology, 29(8), 1836-1842.

Rajpurkar, P., Chen, E., Banerjee, O., & Topol, E. J. (2022). AI in health and medicine. Nature Medicine, 28(1), 31-38.

Tschandl, P., Codella, N., Akay, B. N., Argenziano, G., Braun, R. P., Cabo, H., ... & Kittler, H. (2020). Comparison of the accuracy of human readers versus machine-learning algorithms for pigmented skin lesion classification: an open, web-based, international, diagnostic study. The Lancet Digital Health, 2(1), e28-e37.

Brinker, T. J., Hekler, A., Enk, A. H., Berking, C., Haferkamp, S., Hauschild, A., ... & Utikal, J. S. (2019). A convolutional neural network trained with dermoscopic images performed on par with 145 dermatologists in a clinical melanoma classification scenario. European Journal of Cancer, 111, 48-54.
</p>






















