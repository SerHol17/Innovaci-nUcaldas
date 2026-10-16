---
title: Unidad 3.2 · Metodologías Ágiles: Scrum, Kanban y DevOps
---

# Unidad 3.2 — Metodologías Ágiles: Scrum, Kanban y DevOps

```{admonition} Objetivo de la sección
:class: tip
Entender qué es la agilidad y por qué surgió, dominar el funcionamiento de Scrum, Kanban y DevOps, y desarrollar criterio para elegir cuál (o qué combinación) conviene a cada tipo de proyecto de transformación digital, evitando la aplicación mecánica de rituales sin entender su propósito.
```

La sección 3.1 terminó con una hoja de iniciativas priorizadas. Ahora hay que ejecutarlas, y aquí aparece un problema clásico: los proyectos de transformación digital rara vez tienen requisitos estables. Se descubre qué quiere realmente el usuario cuando ya hay algo en sus manos, la tecnología cambia durante el proyecto, y las prioridades del negocio se mueven. Planificar todo al detalle al inicio, como proponía el enfoque tradicional en cascada (*waterfall*), funciona bien cuando los requisitos son conocidos y estables, y funciona mal cuando no lo son. Las metodologías ágiles nacieron precisamente como respuesta a ese problema.

## Qué es la agilidad

En 2001, un grupo de diecisiete profesionales del desarrollo de software publicó el *Manifiesto Ágil*, que resume la filosofía en cuatro valores: valorar a los **individuos y sus interacciones** por encima de los procesos y las herramientas; el **software funcionando** por encima de la documentación exhaustiva; la **colaboración con el cliente** por encima de la negociación contractual; y la **respuesta ante el cambio** por encima del seguimiento de un plan. El manifiesto aclara que los elementos de la derecha también tienen valor, pero que los de la izquierda se valoran más.

Dos ideas de fondo sostienen todo lo demás. La primera es la **entrega incremental**: en lugar de entregar todo al final de un proyecto largo, se entregan versiones pequeñas y utilizables con frecuencia. La segunda es el **aprendizaje por retroalimentación**: cada entrega se usa para aprender qué funciona y qué no, y ese aprendizaje corrige el rumbo del siguiente ciclo. Todo lo que se verá en esta sección (sprints, tableros, pipelines) son mecanismos para lograr esas dos cosas.

Vale la pena un matiz importante para este curso: aunque la agilidad nació en el desarrollo de software, hoy se aplica a proyectos de marketing, recursos humanos, operaciones y gestión de proyectos de transformación en general. No hace falta programar para usar Scrum o Kanban.

## Scrum

Scrum es el marco ágil más extendido. Su definición oficial está en la *Scrum Guide* (Schwaber y Sutherland, 2020), y se organiza alrededor de ciclos de trabajo de duración fija llamados **sprints**, de un mes como máximo (lo habitual es entre una y cuatro semanas). Al final de cada sprint el equipo debe tener un **incremento** del producto: algo terminado, utilizable y verificable.

### Roles

Scrum define tres responsabilidades, no jerarquías:

- **Product Owner:** responsable de maximizar el valor del producto. Es quien decide qué se construye y en qué orden, administrando el *Product Backlog*. Representa a los interesados (usuarios, negocio) ante el equipo.
- **Scrum Master:** responsable de que el equipo entienda y aplique Scrum, y de remover los obstáculos que le impiden avanzar. No es un jefe de proyecto: no asigna tareas, sirve al equipo.
- **Developers (equipo de desarrollo):** las personas que hacen el trabajo para producir el incremento. Se autoorganizan para decidir cómo cumplir con lo que se comprometieron. El término "developers" incluye a todos los perfiles necesarios (en un proyecto de datos, científicos de datos, ingenieros de datos, analistas), no solo a programadores.

### Eventos

El ciclo de Scrum tiene cinco eventos con duración limitada (*timebox*):

| Evento | Propósito | Duración típica |
|---|---|---|
| **Sprint** | Contenedor de todos los demás eventos; el ciclo de trabajo en sí | 1 a 4 semanas (máximo un mes) |
| **Sprint Planning** (planificación) | Definir qué se va a hacer en el sprint y cómo, estableciendo el *Sprint Goal* | Hasta 8 horas para un sprint de un mes; menos en sprints más cortos |
| **Daily Scrum** (reunión diaria) | Sincronizar al equipo y ajustar el plan de las próximas 24 horas | 15 minutos |
| **Sprint Review** (revisión) | Mostrar el incremento a los interesados y recoger retroalimentación | Hasta 4 horas para un sprint de un mes |
| **Sprint Retrospective** (retrospectiva) | Reflexionar sobre cómo trabajó el equipo y acordar mejoras concretas | Hasta 3 horas para un sprint de un mes |

La retrospectiva merece atención especial porque es el mecanismo de mejora continua del propio equipo: sin ella, Scrum se reduce a un calendario de reuniones.

```{figure} /_static/images/u32-ciclo-scrum.jpg
:name: fig-u32-ciclo-scrum
:alt: Ciclo de Scrum con sus eventos y artefactos
:width: 85%

El ciclo de Scrum: el Product Backlog alimenta la planificación, el sprint produce un incremento, y la revisión y la retrospectiva cierran el ciclo.
```


### Artefactos y compromisos

- **Product Backlog:** lista ordenada y viva de todo lo que se necesita en el producto. Cada elemento suele escribirse como una **historia de usuario**: "Como [rol], quiero [funcionalidad] para [beneficio]". Su compromiso asociado es el *Product Goal*, el objetivo de largo plazo del producto.
- **Sprint Backlog:** los elementos del Product Backlog seleccionados para el sprint, más el plan para entregarlos. Su compromiso es el *Sprint Goal*, el objetivo del sprint.
- **Incremento:** el resultado concreto y utilizable del sprint. Su compromiso es la **Definición de Hecho (*Definition of Done*)**: el acuerdo explícito sobre qué significa que algo esté terminado (por ejemplo, "probado, revisado por un par y documentado"). Sin una definición de hecho clara, "terminado" significa cosas distintas para cada persona.

### Ejemplo aplicado

Retomando la clínica de la sección 3.1, supóngase que la iniciativa priorizada es un tablero de seguimiento de pacientes en riesgo de abandonar su tratamiento. El Product Owner (la coordinadora médica) mantiene un Product Backlog; el equipo selecciona para el primer sprint de dos semanas lo siguiente:

| Historia de usuario | Estimación | Criterio de hecho |
|---|---|---|
| Como coordinadora, quiero ver la lista de pacientes con más de dos citas canceladas, para contactarlos | 5 puntos | Lista visible en el tablero con datos del mes actual, validada por la coordinadora |
| Como coordinadora, quiero filtrar la lista por especialidad, para asignar el seguimiento al equipo correcto | 3 puntos | Filtro funcionando y probado con datos reales |
| Como analista, quiero un proceso automático de carga de datos, para no actualizarlo a mano | 8 puntos | Carga programada diaria con registro de errores |

El *Sprint Goal* podría ser "la coordinadora puede identificar cada mañana a los pacientes en riesgo". Al final del sprint, la revisión muestra el tablero funcionando, la coordinadora da retroalimentación (por ejemplo, que necesita ver también el motivo de cada cancelación), y esa observación entra al Product Backlog para el siguiente sprint. Eso es entrega incremental y aprendizaje por retroalimentación en acción.

## Kanban

Kanban tiene su origen en el sistema de producción de Toyota, donde Taiichi Ohno usaba tarjetas (*kanban* significa "tarjeta visual" en japonés) para señalar cuándo había que reponer material en una línea de producción. David J. Anderson (2010) adaptó esos principios al trabajo del conocimiento y a los equipos de tecnología. A diferencia de Scrum, Kanban no tiene sprints, roles ni eventos obligatorios: es un método para visualizar el trabajo, limitar el trabajo en curso y mejorar el flujo continuamente.

### Prácticas centrales

1. **Visualizar el trabajo:** el trabajo se representa en un tablero con columnas que corresponden a las etapas del proceso (por ejemplo, "Por hacer", "En progreso", "En revisión", "Hecho"), y cada tarea es una tarjeta. Lo que no se ve no se puede gestionar.
2. **Limitar el trabajo en progreso (WIP, *work in progress*):** cada columna tiene un límite máximo de tarjetas simultáneas. Si la columna "En progreso" tiene un límite de tres, nadie puede empezar una cuarta tarea hasta que se termine alguna. Esto parece una restricción, pero es la práctica más potente de Kanban: obliga a terminar antes de empezar, expone los cuellos de botella y reduce el cambio constante de contexto.
3. **Gestionar el flujo:** se miden indicadores como el **tiempo de ciclo** (*cycle time*: cuánto tarda una tarea desde que se empieza hasta que se termina), el **tiempo de entrega** (*lead time*: desde que se solicita hasta que se entrega) y el **rendimiento** (*throughput*: cuántas tareas se terminan por unidad de tiempo).
4. **Hacer explícitas las políticas:** las reglas de cuándo una tarjeta puede pasar de una columna a la siguiente (la definición de "hecho" de cada etapa) se escriben y se acuerdan.
5. **Mejorar de forma colaborativa y evolutiva:** los cambios al proceso son graduales, basados en lo que muestran los datos del flujo.

```{figure} _static/images/u32-tablero-kanban.jpg
:name: fig-u32-tablero-kanban
:alt: Tablero Kanban con columnas y límites de trabajo en progreso
:width: 85%

Un tablero Kanban: las columnas representan las etapas del proceso y el límite de trabajo en progreso (WIP) hace visibles los cuellos de botella.
```

:::{dropdown} Qué debe tener esta imagen
Ilustración de un tablero Kanban, estilo interfaz limpia de herramienta de gestión. Cuatro columnas etiquetadas "Por hacer", "En progreso (WIP máx. 3)", "En revisión (WIP máx. 2)", "Hecho". Tarjetas de colores suaves distribuidas en las columnas; la columna "En revisión" con dos tarjetas y un indicador visual rojo suave que muestre que alcanzó su límite, para ilustrar un cuello de botella. Fondo gris muy claro, tarjetas blancas con bordes de color, proporción apaisada (16:9).
:::

Por qué funciona el límite de WIP tiene una explicación matemática simple, la **Ley de Little**: en un sistema estable, el tiempo promedio que una tarea pasa en el sistema es igual al trabajo en curso dividido entre el rendimiento. Si el equipo termina 4 tareas por semana y tiene 12 en curso, cada tarea tarda en promedio 3 semanas. Si limita el trabajo en curso a 4, y el rendimiento se mantiene, cada tarea tarda en promedio una semana. Empezar menos cosas hace que las cosas terminen antes.

Kanban se adapta bien a trabajo con demanda impredecible y de llegada continua: soporte técnico, mantenimiento, atención de solicitudes, operaciones. Para ese tipo de trabajo, los sprints de duración fija son un ajuste incómodo, porque las solicitudes no esperan al próximo ciclo. Muchos equipos combinan ambos enfoques en lo que se conoce como **Scrumban**: sprints y roles de Scrum con tablero y límites de WIP de Kanban.

## DevOps

Scrum y Kanban organizan el trabajo del equipo. DevOps aborda un problema distinto, el que ocurre en la frontera entre desarrollo y operaciones. Tradicionalmente, el equipo de desarrollo quería entregar cambios rápido, mientras que el equipo de operaciones quería estabilidad y, por tanto, resistía los cambios. Ese conflicto de incentivos generaba entregas lentas, riesgosas y llenas de fricción: el código "funcionaba en mi máquina" y fallaba en producción.

DevOps (de *Development* y *Operations*) es un conjunto de prácticas y una cultura que busca eliminar esa barrera, de modo que el mismo equipo (o equipos muy colaborativos) sea responsable de construir, desplegar y operar un servicio. Kim, Humble, Debois y Willis (2016), en *The DevOps Handbook*, lo organizan en tres principios que llaman las "Tres Vías": **flujo** (acelerar el camino del trabajo desde el desarrollo hasta producción), **retroalimentación** (obtener información rápida y constante de producción para corregir pronto) y **aprendizaje continuo** (cultura de experimentación y de aprender de los errores sin buscar culpables).

### Integración y entrega continuas (CI/CD)

La práctica técnica más característica de DevOps es la automatización del camino que recorre un cambio desde que un desarrollador lo escribe hasta que llega a producción:

- **Integración continua (CI):** cada vez que alguien incorpora un cambio al repositorio compartido, un sistema automatizado compila el proyecto y ejecuta las pruebas. Si algo falla, se detecta en minutos y no semanas después, cuando arreglarlo es más costoso.
- **Entrega continua (CD, *Continuous Delivery*):** cada cambio que pasa las pruebas queda automáticamente listo para ser desplegado a producción, con una decisión humana final de cuándo hacerlo. Humble y Farley (2010) desarrollaron este concepto en su libro *Continuous Delivery*.
- **Despliegue continuo (*Continuous Deployment*):** un paso más, en el que cada cambio que pasa todas las pruebas se despliega a producción automáticamente, sin aprobación manual.

```{figure} _static/images/u32-pipeline-cicd.jpg
:name: fig-u32-pipeline-cicd
:alt: Pipeline de integración y entrega continuas
:width: 90%

El pipeline de CI/CD automatiza el camino de un cambio, desde el código hasta producción, con retroalimentación en cada etapa.
```

:::{dropdown} Qué debe tener esta imagen
Diagrama horizontal de flujo en etapas (pipeline), estilo técnico limpio. Etapas en secuencia con íconos simples: "Código (commit)" → "Compilación" → "Pruebas automáticas" → "Empaquetado" → "Despliegue a pruebas (staging)" → "Despliegue a producción" → "Monitoreo". Debajo del pipeline, una flecha larga de retorno de derecha a izquierda etiquetada "Retroalimentación: si algo falla, el cambio se detiene y se avisa al equipo". Etapas de CI agrupadas con un corchete azul y etapas de CD con un corchete verde. Fondo blanco, proporción apaisada (16:9).
:::

Otras prácticas que acompañan a DevOps son el **control de versiones** de todo (no solo el código), la **infraestructura como código** (*Infrastructure as Code*: definir servidores y redes mediante archivos versionables en lugar de configurarlos manualmente) y el **monitoreo** continuo de los sistemas en producción.

### Cómo se mide DevOps

El programa de investigación DORA (*DevOps Research and Assessment*), recogido por Forsgren, Humble y Kim (2018) en *Accelerate*, identificó cuatro métricas que distinguen a los equipos de alto desempeño en entrega de software:

| Métrica | Qué mide |
|---|---|
| **Frecuencia de despliegue** | Con qué frecuencia el equipo despliega a producción |
| **Tiempo de entrega de cambios** | Cuánto tarda un cambio desde que se confirma en el código hasta que está en producción |
| **Tasa de fallos en cambios** | Qué porcentaje de despliegues causa un fallo en producción |
| **Tiempo de recuperación** | Cuánto tarda el equipo en restaurar el servicio cuando algo falla |

Lo interesante de estas métricas es que miden velocidad y estabilidad a la vez. La idea de que hay que sacrificar una para tener la otra es, precisamente, el conflicto que DevOps busca superar.

## Comparación y criterios de elección

Las tres metodologías no son excluyentes ni están en el mismo plano: Scrum y Kanban organizan el trabajo, y DevOps organiza la entrega y la operación. Es muy común usar Scrum o Kanban para gestionar el trabajo del equipo y prácticas DevOps para llevar ese trabajo a producción.

| Aspecto | Scrum | Kanban | DevOps |
|---|---|---|---|
| **Enfoque principal** | Entregar incrementos en ciclos fijos | Optimizar el flujo continuo de trabajo | Acelerar y estabilizar la entrega y operación |
| **Estructura de tiempo** | Sprints de duración fija | Flujo continuo, sin ciclos | Pipeline continuo |
| **Roles** | Product Owner, Scrum Master, Developers | Ninguno obligatorio | Cultura compartida entre desarrollo y operaciones |
| **Mecanismo clave** | Sprint Backlog, eventos con *timebox* | Tablero y límites de WIP | Automatización (CI/CD), infraestructura como código |
| **Cambios a mitad del ciclo** | Se evitan durante el sprint | Se aceptan en cualquier momento | Se despliegan continuamente |
| **Mejor para** | Proyectos con objetivos definibles en incrementos y un equipo estable | Trabajo continuo e impredecible (soporte, operaciones) | Servicios de software que se despliegan y operan con frecuencia |

```{figure} ../_static/images/u32-comparacion-metodologias.jpg
:name: fig-u32-comparacion-metodologias
:alt: Guía de decisión para elegir entre Scrum, Kanban y DevOps
:width: 80%

Una guía de decisión simple para elegir la metodología según la naturaleza del trabajo.
```



## Errores frecuentes al adoptar metodologías ágiles

Adoptar una metodología ágil en una organización es un proceso de transformación en sí mismo, y es fácil quedarse con la forma sin el fondo:

- **Agilidad de fachada (*cargo cult*):** hacer las reuniones y usar el vocabulario (sprints, daily, backlog) sin cambiar la forma de tomar decisiones. Si el equipo no puede decidir cómo hacer su trabajo, o si un jefe cambia las prioridades a mitad del sprint, la estructura de Scrum queda vacía.
- **"Scrum, pero...":** adoptar solo las partes cómodas (los sprints) y omitir las incómodas (las retrospectivas, la definición de hecho), con lo cual se pierde el mecanismo de mejora.
- **Product Owner ausente o sin autoridad:** si quien prioriza el backlog no tiene tiempo ni poder de decisión, el equipo trabaja sin dirección clara.
- **Confundir velocidad con valor:** entregar muchas historias de usuario no sirve si no resuelven el problema del negocio. Esto conecta con la sección 3.1: el backlog debe derivarse de los objetivos estratégicos.
- **Ignorar la dimensión cultural:** la agilidad exige confianza, tolerancia al error y equipos con autonomía real. Es, en el fondo, un tema de gestión del cambio, que se desarrolla en la sección 3.3.
- **Querer aplicar agilidad en todo:** hay trabajo con requisitos estables y bien conocidos, donde un enfoque más secuencial puede ser perfectamente razonable. La agilidad es una herramienta con contexto de uso, no una receta universal.

Las ideas de esta sección tienen una aplicación particularmente relevante para proyectos de inteligencia artificial: un modelo de machine learning tiene requisitos aún más inciertos que el software tradicional (no se sabe de antemano qué desempeño es alcanzable con los datos disponibles) y, una vez desplegado, sigue cambiando porque los datos cambian. La sección 3.4 desarrolla cómo se combinan agilidad y DevOps en ese contexto, bajo el nombre de MLOps.

```{admonition} Para tu proyecto final
:class: important
Para la organización elegida en tu proyecto final: toma la iniciativa de mayor prioridad que identificaste en la sección 3.1 y (1) escribe cinco historias de usuario con el formato "Como [rol], quiero [funcionalidad] para [beneficio]"; (2) define una Definición de Hecho de tres a cinco criterios; (3) arma un tablero Kanban con sus columnas y justifica los límites de WIP que propones; y (4) argumenta si el trabajo de esa iniciativa se gestionaría mejor con Scrum, con Kanban o con una combinación, y si requeriría prácticas DevOps.
```

## Glosario de términos clave

**Agilidad:** enfoque de trabajo basado en la entrega incremental y el aprendizaje por retroalimentación, formalizado en el Manifiesto Ágil (2001).

**Waterfall (cascada):** enfoque secuencial en el que cada fase se completa antes de pasar a la siguiente.

**Scrum:** marco ágil que organiza el trabajo en sprints de duración fija, con tres responsabilidades (Product Owner, Scrum Master, Developers) y cinco eventos.

**Sprint:** ciclo de trabajo de duración fija, de un mes como máximo, que produce un incremento.

**Product Backlog:** lista ordenada de todo lo que se necesita en un producto, mantenida por el Product Owner.

**Historia de usuario:** descripción breve de una funcionalidad desde la perspectiva de quien la necesita ("Como [rol], quiero [funcionalidad] para [beneficio]").

**Definición de Hecho (Definition of Done):** acuerdo explícito sobre los criterios que debe cumplir un trabajo para considerarse terminado.

**Kanban:** método de gestión del flujo de trabajo basado en visualizar el trabajo y limitar el trabajo en progreso.

**WIP (Work in Progress):** cantidad de tareas en curso al mismo tiempo; limitarla es la práctica central de Kanban.

**Tiempo de ciclo y tiempo de entrega (cycle time, lead time):** medidas del tiempo que tarda una tarea en completarse, desde su inicio o desde su solicitud, respectivamente.

**Scrumban:** combinación de elementos de Scrum y Kanban.

**DevOps:** conjunto de prácticas y cultura que integra desarrollo y operaciones para acelerar y estabilizar la entrega de software.

**CI/CD:** integración continua y entrega (o despliegue) continua; automatización del camino de un cambio desde el código hasta producción.

**Infraestructura como código:** práctica de definir y gestionar la infraestructura mediante archivos versionables en lugar de configuración manual.

**Métricas DORA:** cuatro métricas (frecuencia de despliegue, tiempo de entrega de cambios, tasa de fallos en cambios y tiempo de recuperación) que miden el desempeño de la entrega de software.

## Preguntas de repaso

1. Explica con tus palabras por qué el enfoque en cascada funciona mal cuando los requisitos son inciertos, y qué ofrece la entrega incremental para resolverlo.
2. En Scrum, ¿en qué se diferencia el rol del Scrum Master del de un jefe de proyecto tradicional? ¿Por qué esa diferencia importa?
3. ¿Por qué limitar el trabajo en progreso en un tablero Kanban puede hacer que las tareas se terminen antes, aunque parezca contraintuitivo? Apóyate en la Ley de Little.
4. Describe qué ocurre en un pipeline de CI/CD cuando una prueba automática falla, y por qué eso es una ventaja frente a descubrir el error semanas después.
5. Una unidad de atención al cliente recibe solicitudes todos los días, de forma impredecible, y quiere mejorar su tiempo de respuesta. ¿Scrum o Kanban? Justifica tu elección.
6. Menciona dos señales de que una organización está aplicando "agilidad de fachada" y propón una acción para corregir cada una.

## Referencias de la sección

- Beck, K., et al. (2001). *Manifiesto por el Desarrollo Ágil de Software* (Agile Manifesto). agilemanifesto.org.
- Schwaber, K., & Sutherland, J. (2020). *La Guía de Scrum* (Scrum Guide). scrumguides.org.
- Anderson, D. J. (2010). *Kanban: Successful Evolutionary Change for Your Technology Business*. Blue Hole Press.
- Humble, J., & Farley, D. (2010). *Continuous Delivery: Reliable Software Releases through Build, Test, and Deployment Automation*. Addison-Wesley.
- Kim, G., Humble, J., Debois, P., & Willis, J. (2016). *The DevOps Handbook: How to Create World-Class Agility, Reliability, and Security in Technology Organizations*. IT Revolution Press.
- Forsgren, N., Humble, J., & Kim, G. (2018). *Accelerate: The Science of Lean Software and DevOps*. IT Revolution Press.
