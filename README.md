# Actividad3_EEDD_PABLOGARRIDOLOPEZ 

# Descripción y Análisis del Diagrama de Casos de Uso

En el marco de este proyecto, se ha desarrollado un diagrama de casos de uso que representa gráficamente la estructura y funcionalidad de una aplicación de gestión de torneos de e-sports. Este diagrama constituye una herramienta fundamental para comprender las distintas interacciones que se producen entre los actores y el sistema, así como las principales funcionalidades que ofrece la aplicación.

## Actores Principales

En el sistema intervienen dos actores claramente diferenciados:

- **Administrador**: Es el responsable de la gestión global de la aplicación. Su rol abarca desde la inicialización del sistema hasta la administración de los diferentes elementos que lo componen. Entre sus funciones se incluyen la configuración de torneos, el registro y validación de equipos participantes, la supervisión de los resultados de cada jornada y la resolución de posibles incidencias que puedan surgir durante el desarrollo de la competición. Además, el administrador posee privilegios especiales que le permiten modificar configuraciones generales del sistema y asegurar su correcto funcionamiento.

- **Capitán de equipo (Usuario)**: Representa a cada uno de los equipos que participan en el torneo. El capitán actúa como intermediario entre el sistema y los miembros de su equipo, siendo responsable de la gestión de su plantilla, la actualización de los datos de su equipo y la consulta de estadísticas y clasificaciones. A diferencia del administrador, sus funciones están restringidas al ámbito de su propio equipo, garantizando así la seguridad y la integridad de la información general del torneo.

## Funcionalidades del Sistema

El sistema no solo permite la interacción manual de los usuarios, sino que también cuenta con una serie de procesos automáticos que garantizan la fluidez y transparencia de la competición:

- **Actualización de clasificaciones**: Tras la finalización de cada jornada y la introducción de los resultados correspondientes, el sistema procesa automáticamente los datos y actualiza la clasificación general de los equipos, reflejando en tiempo real el rendimiento de cada participante.

- **Generación automática de emparejamientos**: Para la organización de las jornadas, el sistema implementa un sistema de competición Suizo. Esta metodología de emparejamientos asegura que los equipos con rendimientos similares se enfrenten entre sí en cada ronda, propiciando enfrentamientos más equilibrados y competitivos. El principio básico del sistema Suizo es que en cada ronda los equipos ganadores se enfrentan entre sí, mientras que los equipos que hayan perdido también se emparejan entre ellos, y así sucesivamente, hasta que únicamente queda un equipo invicto, quien es proclamado campeón.

- **Determinación del equipo ganador**: Una vez finalizadas todas las rondas previstas en el torneo, el sistema analiza los resultados acumulados y determina de forma automática el equipo ganador del campeonato.

- **Entrega de premios**: Complementariamente, el sistema contempla un módulo que permite registrar y gestionar la entrega de premios a los equipos mejor clasificados, cerrando así de manera formal y ordenada el evento.

## Conclusión

El diseño del sistema se ha realizado siguiendo principios de simplicidad, escalabilidad y eficiencia, asegurando que tanto la gestión administrativa como la experiencia del usuario final resulten ágiles e intuitivas. Además, la automatización de procesos clave como la actualización de clasificaciones y la generación de emparejamientos contribuye significativamente a reducir la carga de trabajo del administrador y a minimizar posibles errores humanos, aumentando la fiabilidad general del torneo.

Este enfoque no solo facilita la gestión de torneos de pequeña y mediana escala, sino que también permite, con las adaptaciones pertinentes, su aplicación en competiciones de mayor envergadura.

---

# Descripción y Análisis del Diagrama de Clases

En este proyecto se ha desarrollado un diagrama de clases que define la estructura interna de una aplicación de gestión de torneos de e-sports. El diagrama refleja las principales entidades del sistema, sus atributos esenciales, los métodos más relevantes y las relaciones que existen entre ellas, siguiendo principios de simplicidad, coherencia y responsabilidad única.

## Componentes Principales

- **Torneo**:  
Contiene atributos básicos (nombre, fechaInicio, email, contraseña) para identificar y gestionar un torneo. Administra las listas de Equipos y Rondas. Los métodos iniciar() y generarPrimerEmparejamientos() permiten controlar el inicio del torneo y crear los primeros enfrentamientos de forma organizada. Se eligió agrupar Equipos y Rondas dentro de Torneo usando listas, ya que son elementos dinámicos y variables en cantidad.

- **Equipo**:  
Cada equipo tiene atributos como nombre, su lista de Jugadores, y variables de control de rendimiento: victorias, empates y derrotas. Los métodos registrarJugador() y consultarScore() permiten gestionar la plantilla y consultar el total de puntos. Se optó por guardar el número de victorias, empates y derrotas de forma separada para facilitar cálculos de clasificación y ofrecer estadísticas más completas.

- **Jugador**:  
Atributos simples (nickname y rol) que caracterizan al jugador y su relación directa con un Equipo. Métodos como actualizarNickname() y actualizarRol() permiten cambios en el perfil del jugador sin modificar la integridad del sistema.

- **Ronda**:  
Encapsula la lista de Partidas que forman una jornada. Sus métodos (generarEmparejamientos(), actualizarClasificacion(), finalizarRonda(), declararCampeon()) gestionan la dinámica de cada fase del torneo. Se representa como una entidad independiente para mantener la flexibilidad de la competición y controlar cada jornada de manera autónoma.

- **Partida**:  
Relaciona dos equipos enfrentados, guarda el resultado y actualiza automáticamente las estadísticas de los equipos mediante registrarResultado(). Se decidió centralizar esta lógica en Partida para evitar que los Equipos tuvieran que interpretar los resultados, asegurando una mayor cohesión.

## Relaciones y Multiplicidades

- Un Torneo gestiona múltiples Equipos y Rondas (1 - n).
- Una Ronda gestiona múltiples Partidas (1 - n).
- Cada Equipo incluye varios Jugadores (1 - n).

Se utilizan relaciones de composición (rombo negro) entre Torneo-Ronda y Ronda-Partida para representar dependencias fuertes: una Ronda no puede existir sin su Torneo, ni una Partida sin su Ronda.

## Conclusión final

El trabajo con UML en este proyecto ha supuesto un desafío considerable. A pesar de haber seguido los conceptos básicos, en muchos momentos me he sentido desorientado a la hora de trasladar correctamente la lógica del sistema a los diagramas formales.

El proceso de diseño de clases y relaciones ha requerido un esfuerzo continuo de revisión y corrección, lo que me ha permitido identificar la necesidad de seguir profundizando en el manejo de UML para aplicarlo con mayor soltura en el futuro.

Aunque el resultado final espero que cumpla con los objetivos planteados, soy consciente de que todavía existe un amplio margen de mejora en mi comprensión y aplicación de esta herramienta.
