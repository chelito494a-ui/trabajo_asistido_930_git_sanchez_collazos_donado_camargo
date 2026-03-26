![Banner](banner_proyecto.png)
##  **¿En qué consiste el proyecto?**

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
  <img src="https://github.com/nelsondonado/Ciencia-de-datos/blob/main/lesion.jpg" width="45%"/>
  &nbsp;
  <img src="https://github.com/nelsondonado/Ciencia-de-datos/blob/main/lesion_dermatoscopio.jpeg" width="45%"/>
</div>


### Limitaciones del enfoque tradicional
<p>
 El enfoque tradicional presentaba múltiples limitaciones: alta variabilidad inter‑observador (concordancias del 60‑70% en lesiones pigmentadas), dependencia de la experiencia del especialista, barreras de acceso en zonas con escasez de dermatólogos y diagnóstico tardío. El melanoma detectado en etapa temprana alcanza >95% de supervivencia a 5 años, mientras que en etapas avanzadas la supervivencia cae por debajo del 20%.
</p>

<div align="center">
  <img src="https://conecta.msd.com.ar/wp-content/uploads/sites/11/2022/10/melanoma-grafico.jpg" width="70%" alt="Supervivencia del melanoma por estadio" />
  <br />
  <em>Supervivencia a 5 años según el espesor del melanoma al momento del diagnóstico. Fuente: MSD Connect.</em>
</div>


---
## 2. Fundamentos Técnicos: Visión por Computadora y Aprendizaje Profundo
### Redes Neuronales Convolucionales (CNN)
<p>
   El sistema se fundamenta en CNN, arquitecturas inspiradas en el córtex visual. Las capas convolucionales detectan patrones jerárquicos: desde bordes y texturas en las primeras capas hasta estructuras dermatoscópicas complejas (redes pigmentarias, glóbulos) en las más profundas. Las capas de pooling reducen dimensionalidad y las capas completamente conectadas realizan la clasificación final.
</p>

<div align="center">
  <img src="estructura CNN" width="80%" alt="Diagrama de arquitectura CNN" />
  <br />
  <em>Arquitectura típica de una Red Neuronal Convolucional.</em>
</div> 


### Transfer Learning: Fundamentos y aplicación
<p>
   Dada la escasez de datos médicos etiquetados, se emplea transfer learning: se parte de redes pre‑entrenadas en ImageNet. En una primera fase (feature extraction) se congelan las capas convolucionales y se entrenan solo las capas clasificadoras. En una segunda fase (fine‑tuning) se descongelan selectivamente algunas capas para ajustarlas al dominio dermatológico con tasas de aprendizaje reducidas.
</p>

<div align="center">
  <img src="Figura-3-Proceso-de-aprendizaje-machine-learning-y-transfer-learning.png" width="80%" alt="Esquema de Transfer Learning" />
  <br />
  <em>Proceso de transfer learning: desde una red pre‑entrenada en ImageNet hasta la adaptación al dominio dermatológico.</em>
</div>


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


<div align="center">
  <img src="MEMC_Matriz_2.jpg" width="55%" alt="Matriz de confusión del modelo" />
  <br />
  <em>Matriz de confusión.</em>
</div>

<p>
   
</p>

<div align="center">
  <img src="CURVAroc.jpeg" width="55%" alt="Curva ROC multiclase" />
  <br />
  <em>Curva ROC y área bajo la curva (AUC) para cada clase.</em>
</div>

<p>
   
</p>

El sistema se concibe como una herramienta de apoyo diagnóstico, no como sustituto del especialista, permitiendo priorizar casos sospechosos y reducir la carga cognitiva en la atención primaria.
</p>


---

## 4. Resultados, impacto y futuro

Los resultados de este proyecto muestran que el uso de inteligencia artificial para analizar imágenes de la piel puede ser muy preciso al detectar enfermedades como el melanoma. Gracias a diferentes formas de medir su desempeño, se ha comprobado que el sistema puede identificar correctamente las lesiones peligrosas y disminuir los errores, especialmente los casos en los que no se detecta una enfermedad. Esto es muy importante, ya que encontrar estas enfermedades a tiempo puede salvar vidas.

### Impacto en la sociedad actual

- Apoya a los especialistas en la toma de decisiones clínicas 
- Reduce la carga operativa en hospitales 
- Mejora la precisión del diagnóstico inicial 
- Facilita el acceso a la salud en zonas con pocos dermatólogos 

### Futuro

El  avance en la medicina será notorio con: 
Diagnósticos más rápidos y automatizados, mayor precisión gracias a mejores modelos de IA, integración en sistemas médicos y aplicaciones de salud, avances en medicina preventiva y personalizada 

> **Importante Recordar:** Este sistema no debe reemplazar a los médicos, sino que puede actúa como una herramienta de apoyo para mejorar la calidad y eficiencia del diagnóstico.

---


## Referencias

1. Esteva, A., Kuprel, B., Novoa, R. A., Ko, J., Swetter, S. M., Blau, H. M., & Thrun, S. (2017). Dermatologist-level classification of skin cancer with deep neural networks. *Nature*, 542(7639), 115-118.

2. Haenssle, H. A., Fink, C., Schneiderbauer, R., Toberer, F., Buhl, T., Blum, A., ... & Uhlmann, L. (2018). Man against machine: diagnostic performance of a deep learning convolutional neural network for dermal melanoma recognition in comparison to 58 dermatologists. *Annals of Oncology*, 29(8), 1836-1842.

3. Tschandl, P., Codella, N., Akay, B. N., Argenziano, G., Braun, R. P., Cabo, H., ... & Kittler, H. (2020). Comparison of the accuracy of human readers versus machine-learning algorithms for pigmented skin lesion classification: an open, web-based, international, diagnostic study. *The Lancet Digital Health*, 2(1), e28-e37.

4. Brinker, T. J., Hekler, A., Enk, A. H., Berking, C., Haferkamp, S., Hauschild, A., ... & Utikal, J. S. (2019). A convolutional neural network trained with dermoscopic images performed on par with 145 dermatologists in a clinical melanoma classification scenario. *European Journal of Cancer*, 111, 48-54.
















