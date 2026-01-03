# NADIR


Documentación Técnica e Investigación Científica

El proyecto NADIR representa la culminación de un esfuerzo multidisciplinario por integrar la ingeniería de software avanzada con la psicofisiología clínica para abordar la gestión de los trastornos de ansiedad y los ataques de pánico. Este repositorio contiene la documentación técnica detallada y la investigación científica fundamentada del proyecto, incluyendo el marco teórico, la arquitectura de software, los algoritmos de procesamiento de señales y las guías de diseño.

La documentación completa está disponible en línea en [daniellopgon.github.io/NADIR_DOC/](https://daniellopgon.github.io/NADIR_DOC/)

## Visión del Proyecto

La filosofía subyacente al desarrollo de NADIR se basa en la premisa de que la tecnología móvil ubicua puede ser reorientada para servir como un dispositivo de intervención inmediata, democratizando el acceso a técnicas terapéuticas que tradicionalmente requerían equipos costosos y entornos clínicos controlados. El objetivo es proporcionar una herramienta de biofeedback respiratorio en tiempo real que pueda ser utilizada de forma autónoma por personas que experimentan episodios de ansiedad o pánico.

## Arquitectura y Diseño

La arquitectura documentada ha sido concebida siguiendo los principios más estrictos de la ingeniería de software moderna, priorizando la modularidad, la escalabilidad y la mantenibilidad. Se ha adoptado el patrón de arquitectura limpia como esqueleto estructural, lo que permite una separación clara de responsabilidades entre las distintas capas. La implementación se describe en el contexto de Kotlin moderno y Jetpack Compose, aprovechando las capacidades de seguridad de tipos y sintaxis concisa para reducir errores y mejorar la legibilidad.

## Innovación en Biofeedback

El núcleo de la investigación reside en la transformación de sensores inerciales integrados en dispositivos móviles en instrumentos de precisión biométrica. El sistema utiliza el acelerómetro triaxial para detectar y analizar los movimientos mecánicos de la pared torácica y abdominal durante el ciclo respiratorio. Al colocar el dispositivo sobre el torso, se capturan las variaciones sutiles en la inclinación y la aceleración lineal, procesando estas señales mediante algoritmos de filtrado digital y análisis de tendencias para identificar la fase exacta de la respiración y calcular la frecuencia respiratoria en tiempo real.

La innovación más significativa radica en el enfoque de diseño para interfaces no visuales. Reconociendo que durante un ataque de pánico la capacidad de atención visual se ve severamente comprometida, el sistema ha sido diseñado para ser completamente funcional sin necesidad de mirar la pantalla. Esto se logra mediante un sistema de retroalimentación multimodal que integra canales hápticos y auditivos, permitiendo al usuario seguir la guía con los ojos cerrados.

## Privacidad y Seguridad

La privacidad y la seguridad de los datos son pilares fundamentales en el diseño documentado. Se ha optado por un modelo de procesamiento puramente local conocido como Edge Computing, lo que significa que todos los cálculos de frecuencia respiratoria y análisis de patrones se realizan dentro del propio dispositivo del usuario sin que ninguna información sea transmitida a servidores externos o almacenada en la nube. Esta arquitectura garantiza la privacidad absoluta del usuario y asegura que la aplicación sea funcional en entornos sin conectividad a internet.

## Validación Científica

La documentación incluye los estudios sobre la implementación de protocolos clínicos validados por la literatura científica, como la técnica 4-7-8 para la relajación profunda, la respiración cuadrada para la recuperación del enfoque y la respiración coherente para la optimización de la variabilidad de la frecuencia cardíaca. Estos protocolos son administrados por un motor de reglas inteligente que selecciona la técnica más adecuada en función del estado fisiológico detectado del usuario.

## Licencia y Contacto

Todo el material contenido en este repositorio, incluyendo textos, diagramas e investigaciones, está protegido por derechos de autor. Este repositorio es un compendio de conocimiento técnico y científico. Para acceder al producto final o solicitar información adicional sobre el código fuente, contacte con el autor a través del repositorio de GitHub.
