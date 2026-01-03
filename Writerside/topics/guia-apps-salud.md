# Guía de Diseño para Apps de Salud

## Requisitos de Google Play Store

Publicar una aplicación de salud en Google Play requiere cumplir con una serie de políticas específicas diseñadas para proteger la seguridad del usuario y la integridad de sus datos sensibles [65].

### Declaración Obligatoria (Health Apps Declaration)

Todo desarrollador con una aplicación publicada en Google Play debe completar el formulario de declaración de aplicaciones de salud (Health apps declaration) en la Consola de Play. Esto es obligatorio incluso si la app no ofrece ninguna función de salud, en cuyo caso se debe certificar ese hecho [66]. El formulario se encuentra en la Consola de Play, dentro de Política > Contenido de la aplicación. Debes declarar todas las funciones de salud que ofrece tu aplicación, seleccionando entre categorías predefinidas. La declaración se revisa como parte del proceso de aprobación de la app [66].

### Disclaimers Obligatorios

Las aplicaciones que ofrezcan funcionalidad médica pero no estén reguladas como dispositivo médico deben incluir descargos de responsabilidad claros [65]. La aplicación debe incluir un descargo que indique claramente que no es un dispositivo médico y que no diagnostica, trata, cura ni previene ninguna afección médica. También debe recordar a los usuarios que consulten a un profesional de la salud para obtener asesoramiento, diagnóstico o tratamiento médico [65].

### Política de Funcionalidades Médicas

Google Play prohíbe las funcionalidades de salud que sean engañosas o potencialmente dañinas [65]. Las aplicaciones que han recibido autorización regulatoria como dispositivo médico deben poder proporcionar prueba de dicha aprobación si se les solicita. Respecto a la transparencia en hardware y sensores: si la app requiere hardware externo para funcionar, debe declararlo claramente en la descripción y no implicar que funciona de forma independiente. Las apps que usen sensores del dispositivo deben especificar qué modelos son compatibles en la descripción [65].

### Requisitos de Privacidad

El manejo de datos de salud, considerados datos personales y sensibles, está estrictamente regulado [65]. Es obligatorio publicar un enlace a una política de privacidad tanto en la ficha de la aplicación en Play Store como dentro de la app. Esta política debe detallar de manera exhaustiva el acceso, recopilación, uso y compartición de datos de salud [65].

Para permisos que acceden a datos sensibles de salud, la app debe explicar de manera prominente cómo se usarán los datos, describir el tipo de datos a los que se accede, y obtener el consentimiento afirmativo del usuario para dicho uso [70]. Los permisos relevantes incluyen BODY_SENSORS y ACTIVITY_RECOGNITION para sensores y actividad; ACCESS_FINE_LOCATION y ACCESS_BACKGROUND_LOCATION para ubicación; y CAMERA, RECORD_AUDIO y BLUETOOTH_SCAN para medios y comunicación. Solo se deben solicitar los permisos esenciales para la funcionalidad principal de la app. Los permisos no utilizados deben eliminarse [65].

## Diseño Centrado en el Usuario de Salud

Un proceso de Diseño Centrado en el Usuario (DCU) es fundamental para crear aplicaciones de salud que sean útiles, utilizables y efectivas [69]. Este enfoque coloca las necesidades, experiencias y limitaciones de los usuarios finales en el centro de cada etapa de desarrollo [68].

### Principios Generales

La investigación respalda el uso de un enfoque de diseño participativo, involucrando directamente a los usuarios finales en actividades como discusiones en grupo, pruebas de wireframes y sesiones de usabilidad [69]. Este proceso iterativo permite comprender el modelo mental del usuario para procesar información y realizar tareas, identificar preferencias personales y prácticas laborales existentes, y priorizar funciones e información basándose en la frecuencia de uso y la necesidad del usuario, no en suposiciones del desarrollador.

Para aplicaciones de salud mental, estos principios se traducen en empatía y comprensión (diseñar a partir de una comprensión profunda de las condiciones, desencadenantes y mecanismos de afrontamiento específicos de los usuarios), accesibilidad y facilidad de uso (priorizar diseños intuitivos, lenguaje claro y acceso rápido a funciones clave, especialmente crucial durante momentos de angustia), e inclusividad (asegurar que la aplicación atienda a una amplia gama de usuarios, considerando diversos orígenes culturales, grupos de edad y necesidades de accesibilidad) [68].

### Lenguaje

El lenguaje debe ser fácil de entender, evitando jerga médica innecesaria. Las pautas de diseño de Google para Health Connect enfatizan la transparencia y la claridad para explicar conceptos clave [70]. Al presentar funciones, se debe articular claramente el beneficio para el usuario. Por ejemplo, en lugar de solo "acceder a datos", explicar "acceder a tus datos de actividad para calcular las calorías quemadas" [70]. Cualquier afirmación o beneficio de salud debe presentarse con honestidad. Las directrices recomiendan informar a los usuarios sobre el propósito y beneficios declarados de la app, la base de dichas afirmaciones, los tipos de usuarios a los que va dirigida, y cualquier riesgo asociado a su uso [70].

## Regulación en la UE (2026)

A partir de 2026, Google Play implementará cambios significativos en su política para incorporar la guía del Grupo de Coordinación de Dispositivos Médicos (MDCG) de la Unión Europea, afectando a las aplicaciones dirigidas a usuarios en la UE [65].

En la UE, el software con un propósito médico está regulado por el Reglamento de Dispositivos Médicos (MDR 2017/745). Las nuevas directrices MDCG aclaran que las tiendas de aplicaciones y los propios desarrolladores pueden ser considerados operadores económicos sujetos a este reglamento, con responsabilidades específicas [71].

El impacto incluye una nueva etiqueta de "Dispositivo Médico" que Google Play añadirá para identificar claramente las aplicaciones certificadas como tales en la UE [65]. Además, si tu aplicación está regulada por el MDR/IVDR de la UE y se dirige al Espacio Económico Europeo, deberás proporcionar y hacer pública información específica en tu ficha de Play Store: nombre del fabricante y Número de Registro Único (SRN), descripción clara del dispositivo y su propósito, advertencias para el usuario, un enlace a las Instrucciones de Uso electrónicas (eIFU), y el Número de Identificación Único del Dispositivo (UDI-DI) [66].

Estos cambios subrayan la creciente convergencia entre las políticas de las plataformas y la regulación sanitaria, haciendo esencial que los desarrolladores comprendan y cumplan con ambos conjuntos de requisitos.
