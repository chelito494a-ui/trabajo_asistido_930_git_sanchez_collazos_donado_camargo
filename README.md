![Banner](banner_proyecto.png)
## 🔍 **¿En qué consiste el proyecto?**

Este proyecto consiste en un sistema de **Visión Computacional** que automatiza el análisis dermatológico mediante **Redes Neuronales Convolucionales (CNN)** para identificar anomalías cutáneas. A través del entrenamiento de modelos de **Aprendizaje Profundo (Deep Learning)**, se busca crear una herramienta que funcione como un asistente de diagnóstico preciso. Con el fin de proporcionar una etiqueta diagnóstica preliminar que sirva de apoyo a los profesionales de la salud, permitiendo que la tecnología traduzca patrones visuales complejos en información clínica accionable y confiable. 

Por consiguiente ayuda a reducir la carga operativa de los hospitales y mejorar la precisión del diagnóstico inicial, convirtiendose en una herramienta esencial para modernizar la atención médica preventiva a nivel global.



# **La Ciencia Detrás del Proyecto: Fundamentos Teóricos y Contexto**

---
## 1. El Problema Clínico: Diagnóstico Visual en Dermatología
### Abordaje tradicional del diagnóstico dermatológico
<p >
   Previo al desarrollo de este proyecto, el diagnóstico de enfermedades cutáneas se fundamentaba en la inspección visual directa, el uso de criterios clínicos estandarizados como el sistema ABCD (Asimetría, Bordes, Color, Diámetro) y, en casos de sospecha, la confirmación histopatológica mediante biopsia. Los especialistas realizaban la evaluación con dermatoscopios, dispositivos de aumento que permiten visualizar estructuras subepidérmicas no apreciables a simple vista.
</p>
<div align="center">
  <img src="https://github.com/nelsondonado/Ciencia-de-datos/blob/main/lesion.jpg" width="35%"/>
  &nbsp;
  <img src="https://github.com/nelsondonado/Ciencia-de-datos/blob/main/lesion_dermatoscopio.jpeg" width="35%"/>
</div>

### Limitaciones del enfoque tradicional
<p>
 El enfoque tradicional presentaba múltiples limitaciones: alta variabilidad inter‑observador (concordancias del 60‑70% en lesiones pigmentadas), dependencia de la experiencia del especialista, barreras de acceso en zonas con escasez de dermatólogos y diagnóstico tardío. El melanoma detectado en etapa temprana alcanza >95% de supervivencia a 5 años, mientras que en etapas avanzadas la supervivencia cae por debajo del 20%.

([Aqui se puede insertar un gráfico de supervivencia del melanoma por estadio])
</p>

![Logo](https://conecta.msd.com.ar/wp-content/uploads/sites/11/2022/10/melanoma-grafico.jpg)

---
## 2. Fundamentos Técnicos: Visión por Computadora y Aprendizaje Profundo
### Redes Neuronales Convolucionales (CNN)
<p>
   El sistema se fundamenta en CNN, arquitecturas inspiradas en el córtex visual. Las capas convolucionales detectan patrones jerárquicos: desde bordes y texturas en las primeras capas hasta estructuras dermatoscópicas complejas (redes pigmentarias, glóbulos) en las más profundas. Las capas de pooling reducen dimensionalidad y las capas completamente conectadas realizan la clasificación final.

([Aqui se puede insertar un diagrama de arquitectura CNN]):
</p>

![Logo](https://github.com/nelsondonado/Ciencia-de-datos/blob/main/proceso.png)

### Transfer Learning: Fundamentos y aplicación
<p>
   Dada la escasez de datos médicos etiquetados, se emplea transfer learning: se parte de redes pre‑entrenadas en ImageNet. En una primera fase (feature extraction) se congelan las capas convolucionales y se entrenan solo las capas clasificadoras. En una segunda fase (fine‑tuning) se descongelan selectivamente algunas capas para ajustarlas al dominio dermatológico con tasas de aprendizaje reducidas.

([Aqui se puede insertar un esquema del proceso de transfer learning]): https://www.researchgate.net/publication/356770285/figure/fig1/AS:1098488339279878@1638911437359/Figura-3-Proceso-de-aprendizaje-machine-learning-y-transfer-learning.png
</p>

### Aumento de datos como estrategia de regularización
<p>
   Para maximizar la diversidad del entrenamiento se aplican transformaciones sintéticas: rotaciones, reflejos, ajustes de brillo y contraste, distorsiones elásticas. Cada imagen se presenta con variaciones en cada época, reduciendo el sobreajuste.
</p>

---
## 3. Métricas de Evaluación en Contexto Clínico
<p>
   La evaluación del sistema desarrollado no se limitó a métricas generalistas como la precisión global, sino que se orientó hacia indicadores con significado clínico específico, reconociendo que las consecuencias de los errores diagnósticos no son simétricas.
</p>
   
   #### - Sensibilidad (Recall):
   <p>
      Proporción de verdaderos positivos sobre el total de casos positivos reales. Es prioritaria para lesiones malignas como el melanoma, donde un falso negativo puede ser fatal.
      </p>
   
   #### - Especificidad:
   <p>
       Proporción de verdaderos negativos sobre el total de casos negativos reales. Es relevante para evitar biopsias innecesarias y falsas alarmas.
       </p>

   #### - Área bajo la curva ROC (AUC-ROC):
   <p>
      Evalúa el poder discriminatorio del modelo independientemente del umbral de decisión.
     </p>

 
   #### - Valor Predictivo Negativo (VPN):
   <p>
      Proporción de verdaderos negativos sobre el total de negativos clasificados. Es clave en un sistema de triaje, pues indica la confianza cuando el modelo clasifica una lesión como benigna.
      </p>


<p>
   ([Aqui se puede insertar un diagrama de matriz de confusión]): https://dialektico.com/wp-content/uploads/2025/01/MEMC_Matriz_2.jpg

([Aqui se puede insertar una gráfica de curva ROC]): https://sl.bing.net/izGiltHtSkm

El sistema se concibe como una herramienta de apoyo diagnóstico, no como sustituto del especialista, permitiendo priorizar casos sospechosos y reducir la carga cognitiva en la atención primaria.
</p>


















