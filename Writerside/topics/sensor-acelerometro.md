# Sensor Acelerómetro

## Funcionamiento

Un acelerómetro es un transductor que mide la aceleración propia en el espacio. En esencia, funciona midiendo la fuerza inercial ejercida sobre una masa interna cuando el sensor experimenta una aceleración, basándose en el principio de la Segunda Ley de Newton. Los diseños modernos, particularmente en electrónica de consumo y dispositivos portátiles, se basan predominantemente en la tecnología MEMS (Micro-Electro-Mechanical Systems).

Los acelerómetros MEMS típicos constan de una masa sísmica (un pequeño peso) suspendida por estructuras flexibles (como resortes) dentro de una cavidad. Cuando se aplica una aceleración, la fuerza inercial desplaza la masa, y este desplazamiento se mide y convierte en una señal eléctrica. Existen principalmente dos principios para realizar esta medición, siendo el capacitivo el más común en los MEMS de bajo consumo y bajo coste.

### Funcionamiento Capacitivo

La masa sísmica actúa como una de las placas de un condensador. Cuando la aceleración la mueve, la distancia entre esta placa móvil y una placa fija cambia, lo que altera la capacitancia. Un circuito integrado mide este cambio y lo traduce en un valor de aceleración proporcional. Este método es conocido por su buen equilibrio entre sensibilidad, consumo energético y capacidad de fabricación en miniatura.

### Funcionamiento Piezoeléctrico

Utiliza materiales que generan un voltaje eléctrico cuando se someten a tensión mecánica (efecto piezoeléctrico). La masa sísmica aplica fuerza sobre un cristal piezoeléctrico durante la aceleración, y el voltaje generado es proporcional a la fuerza aplicada. Estos sensores suelen ser más robustos y sensibles, ideales para medir vibraciones de mayor frecuencia en entornos industriales.

Una característica fundamental de los acelerómetros es su capacidad para medir tanto la aceleración estática (como la gravedad, para determinar orientación) como la aceleración dinámica (debida al movimiento, impactos o vibraciones).

## Ejes X, Y, Z

Para describir completamente la aceleración en el espacio tridimensional, los acelerómetros modernos son típicamente triaxiales. Esto significa que integran tres sensores independientes orientados ortogonalmente entre sí, siguiendo un sistema de coordenadas cartesianas.

El eje X suele definirse como el eje lateral o de "ancho" del dispositivo. El eje Y suele definirse como el eje longitudinal o de "largo" del dispositivo. El eje Z suele definirse como el eje vertical o perpendicular al plano formado por X e Y.

Cada eje mide la componente vectorial de la aceleración en su propia dirección. La aceleración total (vectorial) que experimenta el sensor es la suma combinada de las lecturas de los tres ejes. Esta configuración permite no solo cuantificar la magnitud de la aceleración, sino también determinar su dirección en el espacio.

Una aplicación clave de la medición triaxial es la detección de inclinación u orientación mediante la gravedad terrestre. Cuando un dispositivo está estático, su acelerómetro mide aproximadamente 1 g (9.81 m/s²) en el eje que apunta hacia el centro de la Tierra. Analizando la distribución de esta fuerza de gravedad en los tres ejes, el software puede calcular los ángulos de pitch (inclinación hacia adelante/atrás), roll (inclinación lateral) y, con limitaciones, yaw (rotación horizontal). Esta funcionalidad es fundamental para el volteo automático de pantalla en teléfonos, controles de movimiento en videojuegos o el monitoreo de posturas.

## Frecuencia de Muestreo

La frecuencia de muestreo (o sampling rate), medida en Hertz (Hz), define cuántas lecturas por segundo toma el acelerómetro. Es un parámetro crítico que establece un balance directo entre la fidelidad de la señal capturada y consideraciones prácticas como el consumo energético, el volumen de datos y la carga computacional.

Un principio fundamental es el teorema de Nyquist-Shannon: para reconstruir una señal digital sin distorsión, la frecuencia de muestreo debe ser al menos el doble de la frecuencia máxima presente en la señal analógica original. Por lo tanto, para capturar vibraciones o movimientos de alta frecuencia con precisión, se requieren frecuencias de muestreo elevadas (cientos o miles de Hz). En contraste, para aplicaciones como el reconocimiento de actividades humanas (HAR) o el conteo de pasos, donde los movimientos son relativamente lentos, frecuencias más bajas pueden ser suficientes y mucho más eficientes.

La investigación reciente, centrada en biomarcadores digitales para aplicaciones clínicas, ha explorado activamente el límite inferior viable. Un estudio de 2025 sobre reconocimiento de actividades humanas concluyó que reducir la frecuencia de muestreo hasta 10 Hz no afectó significativamente la precisión en la clasificación de actividades como caminar, subir escalones o estar sentado [27]. Sin embargo, reducirla a 1 Hz sí deterioró la precisión para actividades más complejas. Este hallazgo sugiere que para muchos contextos de monitoreo de salud y actividad a largo plazo, frecuencias de muestreo moderadas (10-50 Hz) ofrecen un equilibrio óptimo entre precisión y eficiencia.

### Guía para la Selección de Frecuencia de Muestreo

Para el rango de 1 Hz a 25 Hz, las aplicaciones típicas incluyen monitoreo de actividad básica (sedentarismo/caminar), estudios de sueño y conteo de pasos. El consumo es muy bajo, pero puede perder detalles de movimientos rápidos o transiciones.

Para el rango de 25 Hz a 100 Hz, las aplicaciones típicas incluyen reconocimiento de actividad humana detallado, detección de caídas y análisis de marcha. Este es el equilibrio óptimo para muchas aplicaciones biomédicas, suficiente para capturar la mayoría de los movimientos humanos voluntarios.

Para el rango de 100 Hz a 400 Hz, las aplicaciones típicas incluyen análisis deportivo (carrera, salto) y monitoreo de vibraciones industriales de baja/media frecuencia. Requiere más energía y capacidad de procesamiento, pero es necesario para capturar movimientos cíclicos rápidos.

Para frecuencias superiores a 400 Hz, las aplicaciones típicas incluyen análisis de impacto (choques), vibraciones de maquinaria de alta velocidad y pruebas estructurales. El consumo es alto y genera grandes volúmenes de datos, pero es esencial para fenómenos de alta frecuencia.
