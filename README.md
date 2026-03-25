![Banner](<img width="1920" height="1080" alt="Banner Git" src="https://github.com/user-attachments/assets/34909f03-e843-4b11-8373-ec01a2fa0b02" />
)
## Detección de enfermedades en la piel
### Realizado por los investigadores Jhonier Francisco Guerrero Gaviria y Brayan David Loaiza Burbano
<p >
   Este proyecto consiste en el desarrollo y entrenamiento de un sistema de Visión Computacional diseñado para el análisis automatizado de imágenes dermatológicas. Utiliza algoritmos de Aprendizaje Profundo (Deep Learning), específicamente Redes Neuronales Convolucionales (CNN), para identificar patrones visuales, texturas y anomalías en la piel que son característicos de diversas condiciones médicas.
  
  El sistema aborda la dificultad del diagnóstico visual manual, el cual puede ser subjetivo y propenso a errores humanos, especialmente en etapas tempranas. Resuelve la necesidad de una herramienta de triaje digital que permita filtrar casos sospechosos de manera rápida, consistente y escalable, reduciendo la carga de trabajo en la inspección inicial de imágenes.
  
  El objetivo principal es desarrollar un modelo de clasificación de imágenes capaz de detectar e identificar con alta precisión distintas enfermedades cutáneas, proporcionando una etiqueta diagnóstica preliminar que sirva como apoyo a la toma de decisiones clínicas.
  
  La relevancia de este proyecto radica en la detección temprana, factor crítico para el éxito del tratamiento en enfermedades graves como el melanoma. Además, democratiza el acceso a evaluaciones preliminares de salud en zonas con escasez de especialistas, permitiendo que un análisis técnico basado en datos mejore significativamente los tiempos de respuesta y la precisión diagnóstica en dermatología.
</p>



#La Ciencia Detrás del Proyecto: Fundamentos Teóricos y Contexto

##1. El Problema Clínico: Diagnóstico Visual en Dermatología
###Abordaje tradicional del diagnóstico dermatológico
<p >
   Previo al desarrollo de este proyecto, el diagnóstico de enfermedades cutáneas se fundamentaba en un proceso clínico que combinaba la inspección visual directa, la evaluación de criterios clínicos estandarizados y, en casos de sospecha, el análisis histopatológico mediante biopsia. Los especialistas realizaban la evaluación de lesiones cutáneas utilizando dermatoscopios, dispositivos de aumento que permiten visualizar estructuras subepidérmicas no apreciables a simple vista, aplicando sistemas de clasificación como el criterio ABCD (Asimetría, Bordes, Color, Diámetro) para la identificación de melanomas.

([Aqui se puede insertar una imagen que muestre la comparación entre una lesión observada a simple vista versus la misma lesión observada con dermatoscopio, evidenciando las estructuras subepidérmicas que son visibles únicamente con aumento])
</p>

###Limitaciones del enfoque tradicional
<p>
   El abordaje tradicional presentaba múltiples limitaciones que este proyecto busca atender. En primer lugar, la subjetividad inherente al diagnóstico visual generaba variabilidad inter-observador significativa, con estudios que reportan concordancias entre dermatólogos tan bajas como el 60-70% para lesiones pigmentadas. En segundo lugar, la precisión diagnóstica dependía fuertemente de la experiencia clínica del especialista, existiendo diferencias sustanciales entre dermatólogos generales y subespecialistas en dermatoscopia oncológica.

([Aqui se puede insertar un gráfico o diagrama que ilustre la variabilidad inter-observador en el diagnóstico dermatológico, mostrando cómo diferentes especialistas pueden clasificar la misma lesión de manera distinta])

En tercer lugar, las barreras de acceso a atención especializada constituían un problema estructural. En regiones apartadas o países en desarrollo, la densidad de dermatólogos era insuficiente para atender la demanda poblacional, generando retrasos en la derivación y el diagnóstico. Finalmente, el diagnóstico tardío representaba la consecuencia más grave de estas limitaciones: mientras que el melanoma detectado en etapas tempranas (espesor <1mm) alcanza tasas de supervivencia superiores al 95% a cinco años, su detección en etapas avanzadas reduce esta cifra por debajo del 20%.

([Aqui se puede insertar una infografía que compare las tasas de supervivencia del melanoma según el estadio de detección, evidenciando la importancia crítica del diagnóstico temprano])
</p>


##2. Fundamentos Técnicos: Visión por Computadora y Aprendizaje Profundo
###Redes Neuronales Convolucionales (CNN)
<p>
   El sistema desarrollado por los investigadores se fundamenta en Redes Neuronales Convolucionales, una clase de modelos de aprendizaje profundo inspirados en la organización del córtex visual de los mamíferos. Estas arquitecturas están diseñadas específicamente para procesar datos con estructura de cuadrícula, como las imágenes dermatológicas.

([Aqui se puede insertar un diagrama esquemático de la arquitectura de una Red Neuronal Convolucional, mostrando las capas de entrada, capas convolucionales, capas de pooling y capas completamente conectadas])

Las CNN operan a través de tres componentes fundamentales. Las capas convolucionales aplican filtros que se deslizan sobre la imagen para detectar patrones espaciales: en las primeras capas se identifican características de bajo nivel como bordes, texturas y colores; en capas más profundas, estas características se combinan para detectar estructuras de alto nivel como redes pigmentarias, puntos y glóbulos característicos de distintas condiciones dermatológicas.

([Aqui se puede insertar una visualización de las activaciones de una CNN, mostrando cómo las primeras capas detectan bordes y texturas simples mientras que las capas más profundas detectan estructuras complejas como redes pigmentarias])

Las capas de pooling reducen la dimensionalidad espacial, disminuyendo la carga computacional y otorgando invarianza traslacional. Finalmente, las capas completamente conectadas integran las características aprendidas para realizar la clasificación final mediante combinaciones no lineales.
</p>

###Transfer Learning: Fundamentos y aplicación
<p>
   El entrenamiento de una CNN desde cero requiere conjuntos de datos masivos, recursos computacionales extensos y presenta alto riesgo de sobreajuste cuando los datos son limitados. Ante esta realidad, los investigadores implementaron la estrategia de transfer learning, que consiste en aprovechar redes neuronales previamente entrenadas en conjuntos masivos como ImageNet (14 millones de imágenes, 1000 categorías) para transferir el conocimiento adquirido hacia el dominio dermatológico.

([Aqui se puede insertar un diagrama conceptual del proceso de Transfer Learning, mostrando cómo una red entrenada en ImageNet se adapta al dominio dermatológico mediante fine-tuning])

Esta estrategia se implementó mediante dos fases. En la primera fase, denominada feature extraction, se congelaron las capas convolucionales pre-entrenadas y se entrenaron únicamente las capas clasificadoras añadidas. En la segunda fase, conocida como fine-tuning, se descongelaron selectivamente algunas de las últimas capas convolucionales para reentrenarlas con tasas de aprendizaje reducidas, permitiendo que la red ajuste sus detectores de características para capturar patrones específicamente dermatológicos.
</p>

###Aumento de datos como estrategia de regularización
<p>
   Dada la limitación inherente de los datasets médicos, los investigadores implementaron técnicas de aumento de datos para maximizar la diversidad del conjunto de entrenamiento. Mediante transformaciones que incluyen rotaciones, reflejos horizontales y verticales, desplazamientos, ajustes de brillo y contraste, y distorsiones elásticas, cada imagen de entrenamiento se presenta al modelo con variaciones sintéticas en cada época, exponiéndolo a una diversidad mayor que la disponible originalmente y reduciendo el riesgo de sobreajuste.

([Aqui se puede insertar una imagen compuesta que muestre múltiples variaciones aumentadas de una misma lesión dermatológica original: rotación, reflejo, ajuste de brillo, distorsión elástica, etc.])
</p>


##3. Métricas de Evaluación en Contexto Clínico
<p>
   La evaluación del sistema desarrollado no se limitó a métricas generalistas como la precisión global, sino que se orientó hacia indicadores con significado clínico específico, reconociendo que las consecuencias de los errores diagnósticos no son simétricas.
</p>
   - ####Sensibilidad (Recall):
   <p>
      Definida como la proporción de verdaderos positivos sobre el total de casos positivos reales. Esta métrica adquiere prioridad crítica para lesiones malignas como el melanoma, donde un falso negativo (no detectar una lesión maligna) puede tener consecuencias fatales para el paciente.
   </p>
   - ####
























