# Guía de Diseño para Interfaces de Ansiedad

## Psicología del Color

El color es una herramienta fundamental que va más allá de la estética, influyendo directamente en las emociones, el comportamiento y la percepción de los usuarios [72][75]. Para una aplicación enfocada en la ansiedad, la elección de la paleta cromática debe realizarse con la intención clara de transmitir calma, seguridad y claridad, evitando estímulos visuales que puedan aumentar la sensación de estrés o sobrecarga [73][74].

### Colores Recomendados

Los azules en tonos suaves a medios transmiten calma, confianza y serenidad. La investigación ha demostrado que los entornos azules pueden reducir la frecuencia cardíaca y la respiración, promoviendo la relajación [73]. Son ideales para fondos, botones primarios y áreas que requieren concentración.

Los verdes en tonos apagados y naturales se asocian con la naturaleza, el crecimiento, el equilibrio y la tranquilidad [73]. Funcionan muy bien como color secundario, para acentos, iconos o para secciones relacionadas con el progreso y el bienestar general.

Las lavandas y morados suaves combinan la estabilidad del azul con un toque de calidez. Evocan espiritualidad, calma y creatividad, siendo adecuados para espacios de meditación o reflexión [73].

Los neutros cálidos como blancos rotos, grises claros y beiges proporcionan un lienzo limpio, transmiten simplicidad y apertura, y reducen la fatiga visual. Son la base para una interfaz minimalista y no sobrecargada [72][74].

### Colores a Evitar

Los rojos intensos y naranjas brillantes, aunque pueden significar energía y urgencia en otros contextos, en una app para la ansiedad pueden percibirse como agresivos, estresantes o asociados al peligro [73]. Su uso debe ser muy limitado y estratégico.

Los amarillos vibrantes culturalmente se vinculan a la felicidad, pero en interfaces digitales su exceso puede causar fatiga ocular y, en algunos contextos, asociarse con la ansiedad [72][73].

El negro puro como fondo extensivo puede resultar duro, aumentar el contraste excesivo y, en algunas culturas, tener connotaciones negativas [72]. Es preferible utilizar grises oscuros profundos.

Los colores neón y combinaciones de alto contraste pueden resultar visualmente agresivos, poco profesionales y abrumadores para un usuario en estado de vulnerabilidad [72].

### Paleta Sugerida para NADIR

Para el color primario se recomienda Azul Sereno (#4A7B9D), que transmite confianza y se usa en botones de acción principal, barra de navegación y acentos clave. El color secundario es Verde Musgo Apagado (#6B8A7A), que representa equilibrio y se aplica en botones secundarios, indicadores de éxito e iconos de crecimiento. El terciario es Lavanda Suave (#B8A9D9), que evoca calma y sirve para fondos de tarjetas, ilustraciones y elementos decorativos. El fondo claro en modo día es Blanco Roto (#F5F7FA), que reduce el brillo respecto al blanco puro. El fondo oscuro en modo noche es Gris Carbón Oscuro (#1E2A32), evitando el negro puro. El texto sobre fondo claro usa Gris Pizarra (#2C3E50) y sobre fondo oscuro Gris Plata Apagado (#ECF0F1).

Es crucial validar el contraste entre texto y fondo con herramientas como WebAIM Contrast Checker para cumplir con los estándares WCAG (mínimo 4.5:1 para texto normal) [77]. Evita comunicar información solo mediante color; usa siempre iconos o etiquetas de texto como apoyo [73].

## Elementos de Interfaz

El diseño de la interfaz debe priorizar la claridad, la previsibilidad y la reducción de la carga cognitiva. El objetivo es crear un entorno digital que sea un refugio, no una fuente adicional de estrés [74].

### Layout

La jerarquía visual clara se logra usando el espacio, el tamaño y el contraste de color para guiar la atención del usuario de forma natural hacia lo más importante en cada pantalla. El espacio en blanco generoso permite "respirar" a la interfaz, reduce la sensación de agobio y ayuda al usuario a enfocarse en una tarea a la vez [74]. La consistencia radical en los patrones de navegación, la ubicación de los elementos y los comportamientos de interacción asegura que todo sea predecible en toda la aplicación, ya que la incertidumbre es un detonante de ansiedad. La simplicidad estructural evita menús profundos y complejos; una estructura plana o de pocos niveles es más fácil de comprender y navegar.

### Botones y CTAs

El texto de los botones debe usar un tono colaborativo y empoderador. En lugar de "Enviar" o "Configurar", prueba con "Vamos a empezar", "Guardar mi progreso" o "Explorar ejercicios" [78]. El diseño visual debe ser tranquilo: bordes ligeramente redondeados, colores de la paleta principal y un tamaño que los haga fáciles de tocar. Deben destacar lo suficiente para ser encontrados, pero sin gritar visualmente. Cada interacción debe ser confirmada con una respuesta sutil (feedback háptico y visual inmediato) para que el usuario sepa que su acción fue registrada [77].

### Animaciones

Las animaciones deben ser suaves y con propósito. Utiliza transiciones fluidas (fade, deslizamiento) para guiar la atención entre pantallas de forma natural. Las animaciones deben sentirse "lentas emocionalmente", promoviendo la calma. Las microinteracciones alentadoras, como un sutil rebote o un destello al completar un registro diario, pueden generar una sensación de logro y reforzar hábitos positivos [76]. Están prohibidas las animaciones parpadeantes, repetitivas, demasiado rápidas o que aparecen de forma sorpresiva. Deben estar siempre bajo el control implícito del usuario.

### Modo Oscuro

El modo oscuro es más que una tendencia: es una funcionalidad de bienestar y accesibilidad que debe diseñarse con el mismo cuidado que el modo claro [79]. Utiliza grises profundos, no negro puro, para reducir el contraste agresivo contra el texto blanco y minimizar la fatiga ocular en entornos de poca luz [80]. Los colores de acento de la paleta pueden necesitar un ajuste de saturación o brillo para ser igualmente efectivos y no vibrar sobre fondos oscuros [79]. La aplicación debe respetar la configuración del sistema operativo, pero siempre ofrecer un interruptor manual dentro de la app. El usuario necesita sentir control sobre su experiencia.

## Tono de Comunicación

El lenguaje es la capa más directa de interacción humano-computadora. En una app para la ansiedad, cada palabra debe ser elegida para construir confianza, seguridad y una sensación de compañía no juzgadora [74].

### Mensajes de la IA y Comunicación General

El tono debe ser empático y validante. En lugar de mensajes genéricos, usa un tono que reconozca la situación: "Parece que hubo un problema al guardar. No te preocupes, lo intentamos de nuevo". Debe ser colaborativo, no directivo. La aplicación debe sentirse como un compañero de viaje, no como un instructor. En lugar de órdenes ("Haz el ejercicio"), plantea invitaciones: "¿Te gustaría probar un ejercicio breve para calmarte?". El lenguaje debe ser claro y positivo, sin jerga médica intimidante. Celebra el esfuerzo, no solo el resultado: "Gracias por tomarte un momento para tu bienestar hoy". Debe ser auténtico y realista, evitando el falso optimismo. Es más valioso un mensaje realista y de apoyo: "Algunos días son más difíciles que otros. Estamos aquí para lo que necesites".

### Qué Evitar

Evita los tonos culpabilizadores o de fracaso. Mensajes como "No has completado tu diario esta semana" generan sentimientos negativos. Mejor: "Tu diario te espera cuando estés listo". Evita la urgencia artificial (FOMO). Tácticas como "¡Oferta por tiempo limitado!" están totalmente contraindicadas, ya que explotan la ansiedad en lugar de aliviarla. Evita las asunciones o generalizaciones. No asumas cómo se siente el usuario. Usa preguntas abiertas en lugar de afirmaciones.
