---
title: Unidad 1 · Introducción a la Transformación Digital
---

# Unidad 1 — Introducción a la Transformación Digital

```{admonition} Objetivo de la unidad
:class: tip
Distinguir transformación digital de digitalización y digitización, reconocer los modelos de referencia para ubicar a una organización en su proceso de transformación, y aprender a mapear el ecosistema de herramientas ya existentes antes de proponer construir una solución desde cero.
```

**Resultados de aprendizaje asociados:** R1 (diseñar estrategias de transformación digital que integren tecnologías emergentes y metodologías ágiles) y R3 (analizar y resolver problemas utilizando herramientas de inteligencia artificial, big data y computación en la nube). Esta unidad sienta la base conceptual sobre la que se construyen las cuatro unidades restantes del curso: sin un vocabulario común, sin un marco para ubicar en qué momento de su proceso está una organización, y sin el criterio de cuándo construir frente a cuándo adoptar algo ya existente, cualquier estrategia posterior corre el riesgo de aplicar la tecnología equivocada al problema equivocado.

## 1.1 Conceptos básicos

Es común escuchar "transformación digital" usado como sinónimo de "comprar software nuevo" o "automatizar un proceso". Esa confusión tiene un costo real: lleva a las organizaciones a invertir en tecnología sin cambiar nada de fondo, y luego a concluir que "la transformación digital no funcionó" cuando en realidad nunca se intentó. Por eso el primer paso de este curso es separar con precisión tres niveles que suelen mezclarse.

**Digitización** es el nivel más básico: convertir información analógica en formato digital, sin alterar el proceso que rodea a esa información. Escanear un contrato en papel y guardarlo como PDF es digitización — el contrato sigue firmándose, archivándose y consultándose exactamente igual que antes, solo que ahora existe también una copia digital. La digitización no cambia cómo se trabaja, solo el soporte de la información.

**Digitalización** va un paso más allá: usa tecnologías digitales para rediseñar y optimizar un proceso existente, sin cambiar el modelo de negocio de la organización. Si ese mismo contrato ahora se genera, se firma electrónicamente y se archiva automáticamente en un sistema de gestión documental, el proceso de "formalizar un contrato" cambió — es más rápido, tiene menos errores, probablemente es más barato — pero la organización sigue haciendo lo mismo que hacía antes, solo que de forma más eficiente.

**Transformación digital** es un cambio estructural en cómo la organización crea y entrega valor, habilitado por la tecnología digital. No se trata de hacer más rápido lo mismo de siempre, sino de preguntarse qué es posible hacer ahora que antes no lo era. Cuando una aseguradora deja de vender pólizas anuales fijas y empieza a cobrar por kilómetro recorrido gracias a sensores IoT en los vehículos de sus clientes, no digitalizó un proceso: transformó su modelo de negocio. La transformación digital casi siempre exige, además de tecnología, cambios en la cultura organizacional, en las capacidades de las personas y en la estructura de la organización.

| Nivel | Qué cambia | Qué NO cambia | Ejemplo |
|---|---|---|---|
| Digitización | El soporte de la información (papel → digital) | El proceso, el modelo de negocio | Escanear facturas en PDF |
| Digitalización | El proceso (más rápido, más barato, con menos errores) | El modelo de negocio | Facturación electrónica automatizada |
| Transformación digital | El modelo de negocio y la forma de crear valor | — (todo puede cambiar) | Cobro de seguro por kilómetro recorrido (pay-per-use) |

```{figure} _static/images/u1-linea-tiempo.jpg
:name: fig-u1-linea-tiempo
:alt: Línea de tiempo con tres etapas: digitización, digitalización y transformación digital
:width: 85%

De la digitización a la transformación digital: tres niveles de madurez tecnológica en una organización.
```


Dos términos adicionales que aparecen con frecuencia en la literatura y que conviene diferenciar desde ya:

**Innovación tecnológica** es la creación o adopción de una tecnología nueva, sin que eso implique necesariamente un cambio de mercado. Una empresa puede innovar internamente (un nuevo algoritmo, una nueva herramienta interna) sin que eso afecte a sus competidores ni a su industria.

**Disrupción digital** ocurre cuando una tecnología cambia las reglas de un mercado completo, dejando en desventaja estructural a los actores que no se adaptan a tiempo. No toda innovación tecnológica es disruptiva, pero toda disrupción digital nace de una innovación tecnológica que encontró una aplicación capaz de redefinir cómo compite una industria entera.

## 1.2 Modelos de transformación digital

Para que una estrategia de transformación digital sea útil, primero hace falta un diagnóstico honesto de en qué punto está la organización. Los marcos de referencia de madurez digital existen justamente para eso: dar un lenguaje común y unos criterios objetivos para ubicar a una organización, en lugar de depender de percepciones subjetivas ("somos bastante digitales" significa cosas muy distintas según quién lo diga).

### El modelo de madurez digital de cinco niveles

Uno de los marcos más usados describe cinco niveles progresivos:

1. **Inicial:** los procesos son mayoritariamente manuales. La tecnología que existe funciona en silos, sin ninguna estrategia que la articule. Las decisiones se toman con información incompleta o desactualizada.
2. **Emergente:** aparecen iniciativas digitales, pero aisladas entre sí — un área automatiza algo, otra compra una herramienta distinta, sin coordinación. No hay gobierno de datos ni una visión compartida de hacia dónde se dirige la digitalización.
3. **Definido:** la organización ya tiene una estrategia digital formal, documentada y comunicada. Sin embargo, su ejecución es desigual: algunas áreas avanzan rápido, otras se quedan atrás, y persisten fricciones entre la estrategia declarada y la práctica diaria.
4. **Gestionado:** la estrategia digital está plenamente integrada a la estrategia de negocio. Existen métricas claras de desempeño digital, gobernanza de datos, y los líderes de todas las áreas (no solo TI) son responsables de avanzar en la transformación.
5. **Optimizado:** la organización itera continuamente sobre sus capacidades digitales. La innovación tecnológica es parte de la cultura, no un proyecto especial; existen mecanismos formales de experimentación (sandboxes, pilotos, áreas de innovación) y la organización aprende de sus fracasos tan rápido como de sus éxitos.

```{figure} _static/images/u1-madurez.jpg
:name: fig-u1-madurez
:alt: Escalera de cinco niveles de madurez digital
:width: 70%

Modelo de madurez digital de cinco niveles.
```


Es importante aclarar que avanzar de nivel no es automático con el paso del tiempo ni con más inversión en tecnología: una organización puede gastar mucho dinero en software y seguir en el nivel "Emergente" si esas inversiones están desarticuladas entre sí.

### Un segundo marco: intensidad digital vs. intensidad de gestión de la transformación

El modelo de cinco niveles es útil como diagnóstico general, pero asume que "madurez digital" es una sola escala. El Center for Digital Business del MIT, en el trabajo que dio origen al libro *Leading Digital* (Westerman, Bonnet y McAfee, 2022), propone un modelo de dos dimensiones que resulta más preciso para diagnosticar organizaciones reales, porque permite que una empresa tenga mucha tecnología y aun así esté mal gestionada digitalmente, o viceversa:

- **Intensidad digital:** cuánta inversión e iniciativas digitales tiene la organización — qué tanta tecnología usa para cambiar cómo opera y cómo compite.
- **Intensidad de gestión de la transformación:** qué tan bien la organización lidera ese cambio — visión compartida, gobernanza, capacidad de coordinar iniciativas entre áreas en lugar de dejarlas aisladas.

Cruzando ambas dimensiones aparecen cuatro perfiles de organización:

| Perfil | Intensidad digital | Intensidad de gestión | Descripción |
|---|---|---|---|
| **Principiantes** | Baja | Baja | Apenas empiezan a explorar qué es posible hacer con tecnología digital; no hay todavía una visión clara. |
| **Fashionistas digitales** | Alta | Baja | Lanzan muchas iniciativas digitales (apps, redes sociales, pilotos de IA) sin una visión integrada; el resultado es una colección de experimentos inconexos, no una transformación. |
| **Conservadores** | Baja | Alta | Tienen gobernanza y disciplina de gestión fuertes, pero son cautelosos con la inversión digital; avanzan despacio pero de forma coordinada. |
| **Digirati** | Alta | Alta | Combinan inversión digital fuerte con una visión de gestión clara y coordinada; son las organizaciones que capturan más valor de negocio por cada iniciativa digital que emprenden. |

Este modelo complementa al de cinco niveles: una organización puede "verse" muy digital (muchas herramientas, mucha tecnología visible) y aun así estar en el cuadrante de "Fashionista digital" si esas iniciativas no están coordinadas — que es, en la práctica, uno de los diagnósticos más comunes en organizaciones que creen estar más avanzadas de lo que realmente están.

### Los cuatro componentes que deben avanzar juntos

Independientemente del marco específico que se use, la literatura coincide en que la transformación digital tiene cuatro componentes que deben evolucionar de manera conjunta:

- **Tecnología:** las herramientas, plataformas e infraestructura digital disponibles.
- **Procesos:** cómo se hace el trabajo — los flujos, las aprobaciones, las dependencias entre áreas.
- **Personas:** las capacidades, habilidades digitales y disposición al cambio de quienes trabajan en la organización.
- **Cultura organizacional:** las creencias y comportamientos compartidos — si se premia la experimentación o se castiga el error, si las decisiones se toman con datos o por jerarquía, si existe colaboración entre áreas.

La causa más frecuente de fracaso en proyectos de transformación digital no es la tecnología elegida, sino el desbalance entre estos cuatro componentes: se invierte fuertemente en tecnología sin invertir en capacitar personas, sin rediseñar procesos y sin atender la cultura que determina si esa tecnología realmente se va a usar.

## 1.3 Aplicaciones en organizaciones

Más allá del marco conceptual, es útil tener claro en qué frentes concretos se traduce la transformación digital cuando se ejecuta bien. No son categorías abstractas: cada una responde a una pregunta de negocio distinta, y conviene mirarlas una por una.

**Mejora de procesos.** La pregunta aquí es "¿cómo hacemos más rápido, más barato o con menos errores algo que ya hacemos?". Un banco que aprobaba créditos de consumo en 10 días hábiles, porque cada solicitud pasaba por revisión manual de varios analistas, puede reducir ese tiempo a minutos si automatiza la verificación de documentos con reconocimiento óptico de caracteres y cruza la información del solicitante contra fuentes de datos ya existentes (centrales de riesgo, historial interno) mediante reglas y modelos predictivos. El proceso de negocio —"aprobar un crédito"— sigue siendo el mismo, pero su costo operativo y su velocidad cambian radicalmente. Este tipo de mejora suele ser el punto de entrada más común a la transformación digital, porque sus resultados son medibles casi de inmediato y no requieren rediseñar el modelo de negocio.

**Creación de valor.** Aquí la pregunta cambia a "¿qué podemos ofrecer ahora que antes era imposible o no rentable?". Una aerolínea tradicional vende tiquetes; una aerolínea que usa datos de comportamiento de sus pasajeros para ofrecer paquetes personalizados de seguros de viaje, alojamiento y transporte terrestre en el momento exacto en que el pasajero está comprando su tiquete está creando una fuente de ingreso que no existía antes, habilitada por la capacidad de procesar datos en tiempo real. La diferencia con la mejora de procesos es que aquí no se está optimizando algo que ya se hacía, sino generando una línea de valor nueva.

**Competitividad.** La pregunta es "¿qué capacidad nos permite responder o anticiparnos mejor que nuestra competencia?". Dos retailers pueden vender exactamente los mismos productos, pero si uno de ellos tiene visibilidad en tiempo real de su inventario en todas sus tiendas y puede redirigir un pedido en línea a la tienda física más cercana con stock disponible, mientras el otro descubre el quiebre de inventario solo cuando el cliente ya canceló la compra, la diferencia no está en el producto sino en la capacidad digital subyacente. Ese tipo de capacidad es difícil de copiar rápido porque no es una sola herramienta, sino la combinación de datos integrados, procesos rediseñados y una cultura que prioriza la velocidad de decisión.

Un buen proyecto de transformación digital casi siempre aporta a más de uno de estos tres frentes simultáneamente: automatizar un proceso de atención al cliente (mejora de procesos) puede, al mismo tiempo, habilitar un nuevo canal de autoservicio (creación de valor) que reduce el tiempo de respuesta frente a la competencia (competitividad). Al evaluar cualquier iniciativa digital —incluidas las que se van a diseñar en el proyecto final de este curso— conviene preguntarse explícitamente a cuál o cuáles de estos tres frentes aporta, porque una iniciativa que no aporta claramente a ninguno probablemente no es una prioridad.

## 1.4 Panorama de herramientas existentes: build vs. buy vs. adopt

Es tentador, sobre todo para perfiles con formación técnica, asumir que la mejor solución a un problema organizacional es construir una herramienta propia. Sin embargo, construir software tiene costos que van mucho más allá del desarrollo inicial: mantenimiento, actualizaciones de seguridad, soporte cuando algo falla, documentación, y el conocimiento que se pierde si la persona que lo construyó deja la organización. Por eso, antes de construir, la pregunta estratégica correcta es: **¿esta necesidad ya está resuelta por alguien más, de forma suficientemente buena y a un costo razonable?**

Esto no significa que construir nunca sea la opción correcta. Significa que construir debe ser una decisión consciente, tomada después de evaluar las alternativas, y no el reflejo por defecto de un equipo técnico.

### El marco build vs. buy vs. adopt

Hay tres caminos posibles frente a una necesidad tecnológica:

**Build (construir):** desarrollar una solución a la medida, desde cero o sobre componentes propios. Tiene sentido cuando la necesidad es altamente específica del negocio, cuando esa capacidad es una fuente real de ventaja competitiva (algo que, si lo tuviera cualquier competidor, no cambiaría nada — en ese caso no vale la pena construirlo propio), o cuando no existe en el mercado ninguna solución que se ajuste ni remotamente al problema.

**Buy (comprar):** adquirir una licencia de un software comercial ya construido (por ejemplo, un ERP como SAP o un CRM como Salesforce) y configurarlo para las necesidades de la organización. Tiene sentido cuando la necesidad es común a muchas organizaciones del mismo tipo (contabilidad, nómina, gestión de clientes) y el valor está en la ejecución operativa, no en la originalidad del proceso.

**Adopt (adoptar):** usar un servicio SaaS (software como servicio) ya existente, normalmente de menor costo de entrada y más rápido de poner en marcha que una licencia empresarial tradicional, pagando por uso o por suscripción (herramientas de automatización como Zapier o Make, plataformas de analítica, servicios de IA generativa expuestos por API). Tiene sentido cuando se necesita velocidad, cuando el presupuesto inicial es limitado, o cuando se quiere validar una idea antes de comprometerse con una inversión mayor.

```{figure} _static/images/u1-build-buy.jpg
:name: fig-u1-build-buy
:alt: Matriz de decisión build vs. buy vs. adopt
:width: 80%

Matriz de decisión: cuándo construir, comprar o adoptar una solución existente.
```

:::{dropdown} Qué debe tener esta imagen
Diagrama de matriz 2x2, estilo diagrama de flujo limpio y moderno. Eje horizontal: "Disponibilidad de soluciones en el mercado" (de bajo, a la izquierda, a alto, a la derecha). Eje vertical: "Especificidad de la necesidad del negocio" (de bajo, abajo, a alto, arriba). Cuatro cuadrantes con etiqueta de texto dentro de cada uno: abajo-izquierda "Evaluar si la necesidad es real", abajo-derecha "Adoptar (SaaS)", arriba-derecha "Comprar y configurar (licencia)", arriba-izquierda "Construir a la medida". Colores neutros (grises) para los ejes, con un color de acento (verde) resaltando el cuadrante "Adoptar". Proporción cuadrada (1:1).
:::

### Categorías de herramientas existentes

Para poder decidir si algo "ya existe", hay que conocer al menos las grandes categorías de software empresarial disponibles hoy:

**ERP (Enterprise Resource Planning):** sistemas que integran la planificación de recursos de una organización — finanzas, inventario, compras, recursos humanos — en una sola plataforma. Ejemplos de la categoría: SAP, Oracle NetSuite, Microsoft Dynamics.

**CRM (Customer Relationship Management):** sistemas enfocados en la relación con el cliente — seguimiento de oportunidades de venta, historial de interacciones, campañas de marketing. Ejemplos de la categoría: Salesforce, HubSpot.

**Plataformas low-code / no-code:** permiten construir aplicaciones internas (formularios, flujos de aprobación, pequeñas apps de gestión) sin necesidad de programar desde cero, usando interfaces visuales. Ejemplos de la categoría: Microsoft Power Apps, Mendix, OutSystems, Airtable. Son especialmente relevantes para transformación digital porque permiten a áreas de negocio, no solo a TI, digitalizar procesos propios con rapidez.

**SaaS de IA y analítica:** servicios ya empaquetados que exponen capacidades de inteligencia artificial o analítica avanzada mediante una interfaz simple o una API, sin que la organización tenga que entrenar modelos propios ni gestionar infraestructura de cómputo. Ejemplos de la categoría: plataformas de analítica de negocio (Power BI, Tableau), APIs de modelos de lenguaje (OpenAI, Anthropic, Google), plataformas de automatización (Zapier, Make).

```{figure} _static/images/u1-panorama.jpg
:name: fig-u1-panorama
:alt: Mapa de categorías de herramientas tecnológicas existentes
:width: 80%

Panorama de categorías de herramientas: ERP, CRM, low-code/no-code y SaaS de IA/analítica.
```

:::{dropdown} Qué debe tener esta imagen
Mapa tipo rueda o mapa mental central, estilo infografía tecnológica moderna. Nodo central con el texto "Ecosistema de herramientas digitales". Cuatro ramas principales saliendo del centro, cada una etiquetada: "ERP", "CRM", "Low-code / No-code", "SaaS de IA y Analítica". Cada rama con 2-3 íconos genéricos representativos de esa categoría (sin logos de marcas reales, solo formas genéricas como engranajes, nubes, gráficos de barras). Paleta azul-morado en degradado, fondo blanco, proporción cuadrada (1:1).
:::

### Criterios de selección

Una vez identificadas las alternativas existentes, hay cuatro criterios centrales para decidir entre ellas (o para justificar que, después de todo, construir es la mejor opción):

**Costo total de propiedad:** no basta con comparar el precio de la licencia o suscripción. Hay que incluir el costo de implementación, de capacitar al equipo, de mantenimiento en el tiempo, y compararlo contra el costo de construir y mantener una solución propia (que incluye salarios de desarrollo, infraestructura, y el costo de oportunidad de no construir otra cosa con ese mismo equipo).

**Escalabilidad:** ¿la herramienta puede crecer junto con las necesidades de la organización, en volumen de datos, número de usuarios o complejidad de los procesos que soporta? Una herramienta que funciona bien para 50 usuarios puede volverse inmanejable o prohibitivamente costosa a 5.000 usuarios.

**Integración:** ¿la herramienta se conecta, mediante API o conectores ya construidos, con los sistemas que la organización ya tiene? Una solución aislada que no comparte datos con el resto de la operación crea un silo nuevo, exactamente el problema que la transformación digital busca evitar.

**Vendor lock-in:** ¿qué tan difícil y costoso sería migrar de esa herramienta hacia otra en el futuro, si la relación con el proveedor cambia, sube de precio o la herramienta deja de evolucionar? Esto incluye tanto la dificultad técnica de exportar los datos como las implicaciones contractuales.

## 1.5 Casos de estudio: éxito y fracaso

### Caso 1 — Netflix vs. Blockbuster

Netflix nació en 1997 como un servicio de alquiler de DVD por correo, compitiendo contra Blockbuster, el líder indiscutido del alquiler de video en tiendas físicas. La disrupción no vino de un solo salto tecnológico, sino de una secuencia: primero el modelo por correo eliminó las multas por retraso y la necesidad de ir a una tienda; después, cuando el ancho de banda de internet lo permitió, Netflix migró a streaming, cambiando de nuevo su modelo de negocio. Blockbuster tuvo la oportunidad de comprar Netflix en el año 2000 por 50 millones de dólares y la rechazó, porque desde su modelo de negocio (ingresos por multas de retraso y alquiler en tienda) el streaming no parecía una prioridad. Blockbuster se declaró en quiebra en 2010. La lección central no es "la tecnología ganó", sino que Netflix rediseñó continuamente su modelo de negocio alrededor de lo que la tecnología hacía posible, mientras Blockbuster optimizó (digitalizó) su modelo existente sin cuestionarlo.

### Caso 2 — Kodak

Kodak inventó la cámara digital en 1975. La empresa tenía la tecnología disruptiva en sus manos casi dos décadas antes que nadie más. Sin embargo, su modelo de negocio dependía de la venta de rollos de película y del revelado de fotos, y promover la fotografía digital significaba canibalizar su propio negocio más rentable. Kodak mantuvo la tecnología archivada internamente mientras protegía su negocio tradicional. Cuando el mercado migró de todas formas hacia lo digital (impulsado por otros fabricantes), Kodak ya no tenía la posición de liderazgo que su invención original le había dado, y se declaró en quiebra en 2012.

```{figure} _static/images/u1-kodak.jpg
:name: fig-u1-kodak
:alt: Comparación entre una cámara análoga y un smartphone, representando la disrupción digital
:width: 75%

La paradoja de Kodak: tener la tecnología no es suficiente si no se transforma el modelo de negocio alrededor de ella.
```

:::{dropdown} Qué debe tener esta imagen
Infografía comparativa de dos columnas, estilo editorial limpio. Columna izquierda: ilustración de una cámara fotográfica análoga clásica, con un ícono de flecha hacia abajo (declive). Columna derecha: ilustración de un smartphone moderno, con un ícono de flecha hacia arriba (crecimiento). Línea divisoria vertical sutil al centro. Paleta neutra (grises) con un color de acento (naranja o rojo) resaltando el contraste entre ambas columnas. Proporción apaisada (16:9).
:::

### Caso 3 — La banca colombiana frente a los neobancos y las fintech

El sistema bancario colombiano tradicional (Bancolombia, Davivienda, BBVA Colombia, entre otros) operó durante décadas con un modelo basado en oficinas físicas, procesos de apertura de cuenta que tomaban días, y productos diseñados para clientes ya bancarizados. A partir de mediados de la década de 2010, surgieron actores digitales — billeteras como Nequi (lanzada por el propio Bancolombia como una unidad separada) y Daviplata, y después fintechs como Lulo Bank y RappiPay — que permitían abrir una cuenta en minutos desde un celular, sin necesidad de ir a una oficina ni cumplir los requisitos tradicionales de vinculación bancaria. Esto fue particularmente relevante en un país con una proporción alta de población no bancarizada o subbancarizada, para quien ir a una oficina física representaba una barrera real. La respuesta de la banca tradicional fue mixta: algunos bancos, como Bancolombia con Nequi, optaron por crear una unidad digital separada con su propia cultura y velocidad de desarrollo, mientras que otros intentaron digitalizar su banca tradicional existente, con resultados más lentos por el peso de procesos y sistemas heredados (legacy). Este caso es relevante para la región porque muestra una tercera vía frente a "digitalizar lo existente" o "ser desplazado": crear una unidad digital independiente, con autonomía para operar con las reglas de un nativo digital, protegida de la inercia organizacional del negocio tradicional.

```{admonition} Guía de discusión en grupo
:class: note
Para cada uno de los tres casos: ¿qué tecnología existía y desde cuándo? ¿qué modelo de negocio tenía el incumbente y por qué ese modelo dificultaba adoptar la tecnología? ¿en qué momento exacto se perdió o se defendió la ventaja, y qué tuvo que cambiar la organización — no solo en tecnología, sino en modelo de negocio y cultura — para lograrlo? Para el caso de la banca colombiana en particular: ¿por qué crear una unidad digital separada (como Nequi) puede ser más efectivo que transformar directamente el banco tradicional?
```

## 1.6 Taller de madurez digital

Este taller aplica lo visto en toda la unidad sobre una organización —real o hipotética— que cada equipo (2-3 estudiantes) elige como caso de trabajo para todo el curso. Tiene cuatro pasos:

**Paso 1 — Diagnóstico de madurez.** Usando el modelo de cinco niveles (sección 1.2), el equipo evalúa en qué nivel se encuentra la organización elegida, por separado para cada uno de los cuatro componentes: tecnología, procesos, personas y cultura. Cada nivel asignado debe estar respaldado por evidencia concreta, no por una impresión general.

**Paso 2 — Identificación de brechas.** A partir del diagnóstico, el equipo identifica entre dos y tres brechas prioritarias — las diferencias más críticas entre el nivel actual y el nivel al que la organización necesitaría llegar para cumplir sus objetivos de negocio.

**Paso 3 — Búsqueda de herramientas existentes.** Para cada brecha priorizada, el equipo busca entre dos y tres herramientas ya existentes en el mercado (dentro de las categorías de la sección 1.4) que podrían cerrarla, y las compara en una matriz usando los cuatro criterios de selección.

```{figure} _static/images/u1-matriz-comparativa.jpg
:name: fig-u1-matriz-comparativa
:alt: Plantilla de matriz comparativa de herramientas
:width: 85%

Plantilla de referencia para la matriz comparativa de herramientas del taller.
```

:::{dropdown} Qué debe tener esta imagen
Imagen de referencia visual de una tabla tipo hoja de cálculo estilizada (ilustrativa, no funcional), con encabezados de columna: "Herramienta", "Costo", "Escalabilidad", "Integración", "Vendor lock-in", "Recomendación". Tres filas de ejemplo con datos genéricos (texto corto tipo "Alto/Medio/Bajo"). Estilo limpio tipo spreadsheet moderno, encabezados en azul, fondo blanco, proporción apaisada (16:9).
:::

**Paso 4 — Recomendación.** Para cada brecha, el equipo redacta una recomendación justificada: construir, comprar o adoptar, explicando por qué esa opción es la más adecuada según los criterios evaluados.

```{admonition} Entregable de la unidad — primer avance del proyecto final
:class: important
Documento breve (1-2 páginas) por equipo con: la organización elegida (sector, tamaño, procesos principales), el diagnóstico de madurez digital por componente, entre dos y tres brechas priorizadas, la matriz comparativa de herramientas para cada brecha, y la recomendación build/buy/adopt justificada. Este documento es la base sobre la que se construirá la estrategia completa en las unidades siguientes.
```

## Glosario de términos clave

**Digitización:** conversión de información analógica a formato digital, sin cambiar el proceso que la rodea.

**Digitalización:** uso de tecnología digital para optimizar un proceso existente, sin cambiar el modelo de negocio.

**Transformación digital:** cambio estructural en cómo una organización crea y entrega valor, habilitado por tecnología digital, que normalmente involucra tecnología, procesos, personas y cultura.

**Innovación tecnológica:** creación o adopción de una tecnología nueva, sin que implique necesariamente un cambio de mercado.

**Disrupción digital:** cambio tecnológico que redefine las reglas de competencia de un mercado completo.

**Madurez digital:** nivel de desarrollo de las capacidades digitales de una organización, medido típicamente en una escala de varios niveles.

**Build vs. buy vs. adopt:** marco de decisión para elegir entre construir una solución a la medida, comprar una licencia de software comercial, o adoptar un servicio SaaS ya existente.

**ERP (Enterprise Resource Planning):** sistema que integra la planificación de los recursos de una organización (finanzas, inventario, recursos humanos) en una sola plataforma.

**CRM (Customer Relationship Management):** sistema enfocado en la gestión de la relación con el cliente.

**Low-code / no-code:** plataformas que permiten construir aplicaciones mediante interfaces visuales, con poca o ninguna necesidad de programación tradicional.

**Vendor lock-in:** dependencia de un proveedor de tecnología que dificulta o encarece migrar hacia una alternativa en el futuro.

**Neobanco:** entidad financiera que opera exclusivamente de forma digital, sin red de oficinas físicas.

## Preguntas de repaso

1. Explica, con un ejemplo propio distinto a los usados en esta unidad, la diferencia entre digitización, digitalización y transformación digital.
2. ¿Por qué una organización puede tener muchas iniciativas digitales y aun así estar en un nivel bajo de madurez según el modelo de cinco niveles? Relaciónalo con el cuadrante "Fashionista digital" del modelo del MIT.
3. De los cuatro componentes que deben avanzar juntos (tecnología, procesos, personas, cultura), ¿cuál consideras que suele recibir menos atención en los proyectos de transformación digital, y por qué?
4. Describe una situación (real o hipotética) en la que la decisión correcta sea "construir" en lugar de "comprar" o "adoptar", y justifica por qué, usando los cuatro criterios de selección vistos en la unidad.
5. Compara el caso de Kodak con el de la banca colombiana frente a los neobancos: ¿qué hizo la banca colombiana distinto de lo que hizo Kodak para no repetir el mismo desenlace?

## Referencias de la unidad

- Rogers, D. L. (2023). *The Digital Transformation Playbook: Rethink Your Business for the Digital Age*. Columbia Business School Publishing.
- Westerman, G., Bonnet, D., & McAfee, A. (2022). *Leading Digital: Turning Technology into Business Transformation* (2nd ed.). Harvard Business Review Press.
- Kane, G. C., Phillips, A. N., Copulsky, J. R., & Andrus, G. R. (2023). *The Technology Fallacy: How People Are the Real Key to Digital Transformation*. MIT Press.
- Ismail, S., Malone, M. S., & van Geest, Y. (2022). *Exponential Organizations: Why New Organizations Are Ten Times Better, Faster, and Cheaper* (Updated Ed.). Diversion Books.
- Wade, M., & Shan, J. (2023). *Hacking Digital: Best Practices to Implement and Accelerate Your Business Transformation*. McGraw-Hill Education.
