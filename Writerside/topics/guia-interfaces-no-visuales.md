# Guía de Diseño para Interfaces No Visuales

## Principios Fundamentales

El diseño de interfaces no visuales se centra en crear experiencias inclusivas que no dependan de la visión como canal primario de interacción. Estos principios son la base para interfaces accesibles que puedan ser utilizadas eficazmente por personas ciegas, con baja visión o en contextos donde la atención visual no está disponible.

Los tres pilares principales son:

1.  Percepción Completa: Toda la información y funcionalidad debe ser presentable al usuario en formas que pueda percibir, independientemente de sus capacidades sensoriales. Esto se logra mediante la redundancia sensorial: ofrecer la misma información a través de múltiples canales (háptico, auditivo, cinestésico) [59].
2.  Operabilidad Universal: Todos los componentes de la interfaz y la navegación deben ser operables a través de varios métodos, sin depender de gestos complejos que requieran coordinación visomotora fina. La interacción debe poder realizarse mediante comandos de voz, gestos hápticos simples, controles físicos o tecnología de asistencia como lectores de pantalla [64].
3.  Retroalimentación Clara y Constante: Proporcionar feedback inmediato, distintivo y significativo por cada acción del usuario es fundamental para construir un modelo mental del sistema y prevenir errores. El usuario debe siempre saber qué está pasando, qué ha hecho y cuáles son sus opciones disponibles [59].

Un principio de diseño clave para interfaces no visuales es el Mapeo Directo: la retroalimentación debe ocurrir en la misma ubicación donde se realizó la acción, siempre que sea posible.

## Feedback Háptico

La retroalimentación háptica utiliza el sentido del tacto para transmitir información. En interfaces no visuales, es especialmente valiosa para proporcionar confirmaciones discretas, comunicar propiedades de objetos virtuales y guiar la atención o navegación sin depender de la vista [61].

### Directrices de Implementación

1.  Mapeo Espacial Directo: La vibración debe originarse lo más cerca posible del punto de interacción táctil. En pantallas táctiles, los actuadores localizados son ideales.
2.  Significado Consistente: Asignar patrones hápticos específicos a tipos de eventos o elementos de la interfaz, y mantener esa asignación en toda la aplicación. Un mismo tipo de error debe sentirse siempre igual [63].
3.  Intensidad y Duración Apropiadas: La vibración debe ser lo suficientemente fuerte para percibirse claramente, pero no tan intensa como para resultar molesta o agotadora con el uso repetido.
4.  Contexto de Uso: Considerar el entorno. En lugares silenciosos, el feedback háptico es ideal para la discreción. En entornos con movimiento, puede necesitarse una vibración más intensa.
5.  Complementariedad, No Saturación: El feedback háptico debe complementar otras modalidades, no duplicarlas innecesariamente. Úsalo para información clave donde el tacto añada valor.

### Patrones Recomendados para NADIR

Basándonos en estándares emergentes y buenas prácticas, se proponen los siguientes patrones hápticos:

1.  Confirmación de Acción Exitosa: Un pulso único, nítido y de duración media (50 ms). Equivalente táctil a un clic satisfactorio.
2.  Navegación entre Elementos/Secciones: Dos pulsos cortos y rápidos (15 ms cada uno, con 20 ms de separación). Indica un paso o movimiento a un ítem adyacente.
3.  Estado Activo o Seleccionado: Una vibración suave y continua de baja amplitud mientras el elemento está enfocado.
4.  Alerta o Recordatorio Amigable: Tres pulsos ascendentes en intensidad. Atrae la atención de forma gradual sin ser alarmante.
5.  Fin de una Actividad Guiada: Una secuencia lenta y rítmica (pulso largo, pausa, pulso largo) que denota calma y culminación.


## Feedback de Audio

La retroalimentación auditiva utiliza sonidos no verbales (earcons) y el habla para comunicar información sobre la interfaz, su estado y los resultados de las acciones del usuario. Es el canal principal para usuarios de lectores de pantalla y una poderosa herramienta de orientación para todos [62].

### Directrices de Implementación

1.  Claridad sobre Realismo: Los sonidos deben ser distintivos y fácilmente reconocibles, no necesariamente realistas. Un beep simple y claro es a menudo más efectivo que un sonido ambiental complejo.
2.  Jerarquía Auditiva: Utiliza diferentes propiedades del sonido (tono, timbre, volumen, patrón rítmico) para denotar importancia. Un evento crítico puede usar un sonido más grave o un patrón de tres tonos.
3.  Control del Usuario: Siempre proporciona controles para ajustar o desactivar los sonidos de la interfaz. Esto es esencial para la accesibilidad y la comodidad personal [58].
4.  Silencio Significativo: El silencio también es información. La ausencia de sonido de confirmación tras una acción puede indicar que la acción no se registró.
5.  Evitar la Sobrecarga Auditiva: No satures al usuario con sonidos constantes. El feedback de audio debe ser breve, relevante y espaciado en el tiempo.

### Estándares de Accesibilidad

El feedback de audio debe implementarse en conformidad con WCAG 2.1. El Criterio 1.4.2 establece que si el audio se reproduce automáticamente durante más de 3 segundos, debe haber un mecanismo para pausarlo, detenerlo o controlar su volumen [58]. El Criterio 1.3.3 indica que las instrucciones no deben depender únicamente de características sensoriales; la información proporcionada por sonidos debe tener una alternativa textual para usuarios sordos o con dificultades auditivas [58].

Es fundamental asegurar la compatibilidad con lectores de pantalla como TalkBack, VoiceOver, NVDA y JAWS. Cualquier elemento interactivo debe tener etiquetas textuales precisas (contentDescription en Android, accessibilityLabel en iOS) que el lector de pantalla pueda anunciar. La estructura de la interfaz debe ser semánticamente correcta para una navegación auditiva eficiente [64]. Los sonidos de la interfaz no deben interferir ni enmascarar el habla del lector de pantalla.

## Diseño Multisensorial

El diseño multisensorial combina de manera armoniosa y redundante el feedback háptico, auditivo y (cuando esté disponible) visual simplificado para crear una experiencia de usuario más robusta, accesible y efectiva que la que cualquier modalidad por sí sola podría proporcionar.

La clave no es sumar señales, sino orquestarlas. Por ejemplo, al recibir un recordatorio en NADIR, el sistema reproduce un earcon corto y melódico mientras el dispositivo vibra con el patrón de alerta amigable (tres pulsos). Si la pantalla está visible, podría mostrar una notificación con alto contraste y texto grande. El cerebro integra estas señales concurrentes, lo que resulta en una percepción más fuerte y clara del evento.

El diseño multisensorial exitoso sigue estas reglas:

1.  Sincronización Temporal: Las señales de diferentes modalidades que se refieren al mismo evento deben coincidir en el tiempo. Un desfase mayor a 100 ms puede hacer que se perciban como eventos separados.
2.  Consistencia Semántica: La sensación emocional o informativa de cada señal debe coincidir. Un sonido suave y relajante debe emparejarse con una vibración igualmente suave, no con una sacudida brusca.
3.  Jerarquía y Redundancia: Decidir qué canal lleva la información primaria. En una interfaz no visual, el audio suele ser primario, el háptico es de apoyo para confirmación y énfasis, y cualquier elemento visual residual actúa como un refuerzo extra para usuarios con visión residual.

Para NADIR, un enfoque multisensorial transforma la interacción. Iniciar una sesión de respiración no sería solo tocar un botón, sino tocar un botón que proporciona un clic háptico satisfactorio, reproduce un tono de inicio suave y es descrito claramente por el lector de pantalla. Este enfoque holístico no solo hace la aplicación más accesible, sino que la hace más inmersiva, efectiva y agradable de usar.
