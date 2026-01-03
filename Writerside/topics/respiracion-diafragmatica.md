# Compendio de Procesamiento de Señales Respiratorias

## 1. Fundamentos de la Señal Respiratoria

La monitorización de la mecánica respiratoria se ha convertido en un componente integral de la salud digital y la computación afectiva. La respiración genera una huella fisiológica compleja capturable a través de múltiples modalidades de sensores. El análisis riguroso abarca la caracterización morfométrica de cada ciclo respiratorio para la detección de eventos discretos y la clasificación de estados patológicos [33].

La señal respiratoria raramente se presenta en forma pura y estacionaria. Independientemente del método de adquisición (ECG, PPG, pletismografía de inductancia, radar UWB, termografía), la señal bruta es una amalgama de actividad fisiológica objetivo, artefactos de movimiento, interferencia electromagnética y modulaciones hemodinámicas concurrentes [33].

### 1.1 Fenomenología de la Modulación Respiratoria

La respiración modula otras señales biológicas mediante tres mecanismos primarios [5]:

1.  Modulación de la Línea de Base: El movimiento de la caja torácica altera la impedancia eléctrica transtorácica y la posición de los sensores respecto al corazón. En ECG, se manifiesta como oscilación de baja frecuencia del eje eléctrico cardíaco. En PPG, las variaciones en presión venosa intratorácica inducen cambios cíclicos en el volumen de sangre basal en tejidos periféricos.

2.  Modulación de Amplitud: La impedancia eléctrica del tórax aumenta durante la inspiración (por el llenado de aire) y disminuye durante la espiración. En ECG provoca variaciones en la amplitud del complejo QRS. En PPG, la reducción de presión intratorácica durante la inspiración aumenta el retorno venoso pero reduce momentáneamente el volumen sistólico.

3.  Modulación de Frecuencia: Conocida como Arritmia Sinusal Respiratoria (RSA), describe la variación de frecuencia cardíaca en sincronía con la respiración: aceleración durante inspiración y desaceleración durante espiración. Los algoritmos que analizan intervalos R-R pueden reconstruir la señal respiratoria basándose en esta modulación cronotrópica [5].

Los algoritmos que integran múltiples fuentes de modulación (AM y FM) superan en precisión a los que dependen de una sola.

### 1.2 Fuentes de Ruido

La "deriva de línea base" no respiratoria comparte un ancho de banda frecuencial cercano al de la respiración fisiológica (0.1 Hz – 0.5 Hz). Los artefactos de movimiento abruptos pueden simular "falsos picos", llevando a sobreestimaciones de la frecuencia respiratoria. En sensores de radar, la señal reflejada contiene componentes de respiración (0.2–0.33 Hz) y latido cardíaco (0.8–2 Hz), requiriendo preprocesamiento espectral meticuloso.

## 2. Preprocesamiento y Acondicionamiento de Señal

### 2.1 Filtrado Espectral y Descomposición Modal

Los filtros FIR/IIR tienen eficacia limitada cuando ruido y señal se solapan en frecuencia. La investigación privilegia métodos de descomposición tiempo-frecuencia.

La Descomposición Modal Empírica (EMD) descompone la serie temporal en Funciones de Modo Intrínseco (IMFs) mediante un proceso de "tamizado". Los componentes de alta frecuencia se segregan en los primeros IMFs, la señal respiratoria en los intermedios, y la deriva de línea base en los residuos finales.

La EMD clásica adolece del problema de "mezcla de modos". Para solventarlo, se emplea CEEMDAN, que añade ruido blanco controlado en cada etapa de descomposición y promedia múltiples realizaciones, logrando separación espectral más limpia [33].

El flujo óptimo para limpieza de ECG/PPG respiratorio es: descomposición en IMFs, identificación de ruido mediante autocorrelación, umbralización wavelet a IMFs ruidosos, eliminación de deriva (componentes con ZCR extremadamente baja), y reconstrucción sumando IMFs procesados.

### 2.2 Filtrado Adaptativo

Los filtros adaptativos LMS utilizan una señal de referencia externa correlacionada con el ruido pero no con la señal biológica. Un acelerómetro triaxial proporciona esta referencia [21][23]. El filtro ajusta sus coeficientes en tiempo real para sustraer artefactos inducidos por movimiento cinético.

## 3. Algoritmos de Detección de Picos

### 3.1 Algoritmos de Cruce por Cero

El método identifica un pico cuando la derivada de la señal cruza por cero con pendiente negativa. Los algoritmos mejorados incorporan umbralización de magnitud y validación temporal. Este refinamiento eleva la precisión del 45% a más del 96% en entornos controlados [33].

### 3.2 Umbralización Adaptativa

Dada la variabilidad del volumen corriente, los umbrales fijos son inviables. Los algoritmos líderes emplean ventanas deslizantes y estadísticas locales. El algoritmo de Fleming combina criterios de media móvil, histéresis temporal y alternancia estricta pico-valle-pico. El algoritmo "Count-orig" calcula un umbral como fracción (0.2-0.3) de la amplitud del percentil 75 de los picos en la ventana reciente.

### 3.3 Pletismografía de Inductancia (RIP)

Para sistemas de doble banda (tórax y abdomen), el algoritmo BreathFinder localiza respiraciones individuales incluso con artefactos. El cálculo del ángulo de fase cuantifica la asincronía toracoabdominal, indicador de obstrucción de vía aérea o fatiga diafragmática.

## 4. Cálculo de RPM

### 4.1 Dominio del Tiempo

La estimación instantánea se calcula como RPM_inst = 60 / T_BB, donde T_BB es el intervalo entre picos inspiratorios consecutivos. Permite analizar la Variabilidad de la Frecuencia Respiratoria (BRV) y detectar pausas de apnea, pero es sensible a falsos positivos.

### 4.2 Dominio de la Frecuencia

La FFT convierte la señal temporal en espectro de densidad de potencia (PSD). El método de Welch divide la señal en segmentos superpuestos con ventana Hamming y promedia los periodogramas. Se identifica el pico espectral máximo en el rango 4-60 RPM (0.06-1.0 Hz) y se calcula RPM = f_max × 60.

El análisis espectral AR produce espectros más suaves y con picos más definidos, incluso con ventanas de datos cortas.

### 4.3 Fusión

Los algoritmos de mayor rendimiento fusionan múltiples fuentes de modulación y combinan estimaciones temporales y espectrales [5][33].

## 5. Fusión de Datos y Filtrado de Kalman

El Filtro de Kalman es un estimador recursivo óptimo que minimiza el error cuadrático medio. Fusiona estimaciones de RPM de diferentes algoritmos o sensores, ponderándolas según su fiabilidad instantánea [33].

La innovación crítica es la modificación adaptativa de la covarianza de ruido de medición basada en un Índice de Calidad de Señal (SQI). Si la señal es perfecta (SQI≈1), el filtro confía en la nueva medición. Si es ruidosa (SQI→0), ignora la medición y confía en su predicción a priori.

Para fusionar múltiples sensores, el sistema calcula un promedio ponderado que penaliza fuertemente a sensores con grandes residuales y baja calidad de señal [33].

## 6. Clasificación de Estados Respiratorios

### 6.1 Patrones Clínicos

1.  Eupnea: Respiración normal (12-20 RPM), rítmica, volumen corriente constante.
2.  Taquipnea: Frecuencia > 20 RPM, a menudo con respiración superficial.
3.  Apnea: Cese del movimiento torácico por ≥10 segundos [29][28].
4.  Cheyne-Stokes: Patrón cíclico crescendo-decrescendo seguido de apnea, marcador de insuficiencia cardíaca [30][28].
5.  Biot: Respiración atáxica por daño neuronal medular, grupos de inspiraciones profundas seguidas de apnea.
6.  Kussmaul: Hiperventilación profunda, regular y rápida, típica de acidosis metabólica severa.

### 6.2 Entropía Aproximada

La variabilidad respiratoria saludable es compleja (alta entropía). En estados patológicos como asma o EPOC, el sistema de control respiratorio pierde complejidad, resultando en disminución de ApEn. Esta métrica puede discriminar obstrucciones de vías aéreas con AUC superior a 0.8 [33].

### 6.3 Aprendizaje Profundo

Las redes 1D-CNN procesan series temporales de sensores inerciales. Un modelo tipo AlexNet adaptado a 1D con 6 capas convolucionales, normalización por lotes, Max-Pooling, Dropout (50%) y regularización L2 ha reportado precisión del 95% en respiración normal y 86% para Apnea Central del Sueño [33].

El algoritmo MLP-Mixer se basa en perceptrones multicapa aplicados sobre parches de la señal. Cualquier evento "apnea" menor a 10 segundos se re-etiqueta como normal o hipopnea, alineando la salida con criterios de diagnóstico clínico [29][28].

Los modelos híbridos integran reglas médicas explícitas en mecanismos de atención de redes LSTM: apnea requiere caída de excursión ≥90% con duración ≥10s [28]; hipopnea requiere caída de flujo ≥30% por ≥10s con desaturación ≥4%. Este enfoque mejora F1-score en 1.78% y precisión en 7.03% sobre modelos de "caja negra" [32].

## 7. Conclusiones

La práctica avanzada emplea extracción híbrida de dominios del tiempo y frecuencia. Los Filtros de Kalman adaptativos guiados por SQI son esenciales para monitorización en el mundo real [33]. Las redes 1D-CNN y MLP-Mixer ofrecen clasificación sin precedentes, pero su adopción clínica depende de integrar capas de reglas médicas explicables [32]. Los algoritmos de preprocesamiento espectral habilitan que sensores de radar y RF sin contacto se conviertan en dispositivos médicos viables.
