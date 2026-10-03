---
title: Unidad 2.3 · Agentes de Inteligencia Artificial
---

# Unidad 2.3 — Agentes de Inteligencia Artificial



```{admonition} Objetivo de la sección
:class: tip
Entender cómo se construye un agente de IA a partir de un modelo de lenguaje: cómo se le instruye (prompting), cómo actúa sobre el mundo real (tool calling), cómo varios agentes pueden colaborar (sistemas multiagentes), y cómo se puede construir todo esto sin programar desde cero (n8n).
```

En la Unidad 2.1 se mencionó que un agente de IA se diferencia de un modelo de machine learning tradicional en que no se limita a producir una predicción puntual: tiene autonomía para encadenar decisiones y perseguir un objetivo de más alto nivel. Esta sección desarrolla en detalle cómo se logra eso en la práctica, y por qué se ha vuelto una de las piezas tecnológicas más relevantes para la transformación digital en los últimos años.

## Prompting: cómo se instruye a un modelo de lenguaje

Antes de hablar de agentes, hay que entender la pieza que los hace posibles: los modelos de lenguaje grandes (LLM, por sus siglas en inglés) y la forma en que se les da instrucciones, conocida como **prompting** o ingeniería de prompts. Un prompt es, en esencia, el texto de entrada que se le da al modelo para obtener una respuesta útil — pero la forma en que se redacta ese texto cambia radicalmente la calidad del resultado.

Un buen prompt suele incluir varios elementos, aunque no todos son necesarios en cada caso:

- **Rol o contexto:** decirle al modelo qué papel debe asumir ("actúa como un analista financiero") o qué contexto de negocio rodea la pregunta.
- **Instrucción clara de la tarea:** qué se le está pidiendo exactamente, evitando ambigüedad.
- **Formato de salida esperado:** si se necesita una lista, una tabla, un número, un texto de cierta longitud.
- **Ejemplos (few-shot):** mostrarle al modelo uno o varios ejemplos de cómo se vería una respuesta correcta, lo cual mejora notablemente la consistencia cuando la tarea es específica o poco común.

```{figure} ../_static/images/u2-prompt-estructura.jpg
:name: fig-u23-prompt-estructura
:alt: Anatomía de un prompt bien estructurado
:width: 80%

Los elementos típicos de un prompt bien estructurado: rol, instrucción, formato esperado y ejemplos.
```



La razón por la que esto importa para la transformación digital no es académica: la diferencia entre un prompt vago y uno bien construido puede ser la diferencia entre una herramienta de IA que genera resultados inconsistentes e inútiles, y una que efectivamente automatiza una tarea de negocio de forma confiable. Buena parte de lo que hoy se llama "ingeniería de IA aplicada" en las empresas consiste, en el fondo, en diseñar y afinar estos prompts para tareas específicas.

Para ilustrar la diferencia, piénsese en una empresa que quiere usar un modelo de lenguaje para clasificar las quejas de sus clientes. Un prompt vago como "clasifica esta queja" producirá respuestas inconsistentes: unas veces el modelo usará categorías distintas, otras veces responderá con una explicación larga en lugar de una categoría, y será casi imposible integrar esa salida a un sistema automatizado. Un prompt bien construido, en cambio, se vería más parecido a esto: "Actúa como un agente de atención al cliente de una empresa de telecomunicaciones. Clasifica la siguiente queja en una de estas categorías exactas: [facturación, calidad de servicio, atención al cliente, otro]. Responde únicamente con el nombre de la categoría, sin explicación adicional. Queja: '{texto del cliente}'." La segunda versión fija el rol, acota las opciones posibles, y especifica el formato exacto de salida — lo que hace que la respuesta sea predecible y fácil de conectar con el resto de un sistema.

Dos técnicas adicionales son particularmente útiles en contextos de negocio:

- **Chain-of-thought (cadena de pensamiento):** pedirle al modelo que razone paso a paso antes de dar la respuesta final, lo cual mejora notablemente el desempeño en tareas que requieren varios pasos de razonamiento (por ejemplo, calcular algo a partir de varias condiciones).
- **Prompts de sistema vs. prompts de usuario:** en la mayoría de las plataformas, existe un prompt "de sistema" que fija el comportamiento general y las reglas que el modelo debe seguir durante toda la conversación (por ejemplo, "nunca reveles información de otros clientes"), separado de los mensajes puntuales del usuario — una distinción importante para pensar en control y seguridad cuando se construye una aplicación real.

## Agentes de inteligencia artificial

Un agente de IA toma un modelo de lenguaje y le da la capacidad de hacer algo más que responder una pregunta: le da **autonomía** para encadenar varias decisiones, **memoria** de lo que ha hecho en los pasos anteriores dentro de una misma tarea, y la posibilidad de **actuar** sobre sistemas externos en lugar de solo producir texto. Mientras un modelo al que se le hace una pregunta puntual responde y termina ahí, un agente puede recibir un objetivo general ("gestiona las solicitudes de devolución que lleguen hoy") y decidir por sí mismo los pasos necesarios para cumplirlo, ajustando su estrategia según lo que vaya encontrando en el camino.

Esta autonomía no es ilimitada ni mágica: en la práctica, un agente sigue un ciclo relativamente simple que se repite — observa el estado actual de la tarea, decide (con ayuda del modelo de lenguaje) cuál es la siguiente acción razonable, ejecuta esa acción, observa el resultado, y vuelve a decidir el siguiente paso, hasta que considera que el objetivo se cumplió o hasta que se le acaban los intentos permitidos.

Un caso real que ilustra bien el impacto de esto a escala es el del banco sueco **Klarna**, que en 2024 puso en producción un asistente de IA para atención al cliente construido sobre un modelo de lenguaje: en su primer mes de operación, ese agente manejó el equivalente al trabajo de 700 agentes humanos de tiempo completo, resolvió consultas en un tiempo promedio de menos de 2 minutos (frente a 11 minutos que tomaba el proceso humano), y atendió en más de 35 idiomas simultáneamente. Lo relevante del caso no es solo el ahorro de costos, sino que Klarna reportó una tasa de resolución comparable a la de sus agentes humanos — lo que demuestra que, para tareas de atención al cliente bien delimitadas (consultas sobre pedidos, devoluciones, facturación), un agente bien diseñado puede operar a un nivel de calidad aceptable para el negocio, no solo como un experimento.

Esto no significa que un agente deba reemplazar sin supervisión cualquier proceso: la decisión de qué tareas delegarle a un agente, y con cuánta autonomía, es en sí misma una decisión estratégica que depende de qué tan costoso es un error (no es lo mismo que un agente se equivoque recomendando un producto, que un agente se equivoque procesando un reembolso o enviando dinero).

## Tool calling: cómo actúa un agente sobre el mundo real

El mecanismo concreto que le permite a un agente dejar de ser "solo texto" y empezar a actuar se llama **tool calling** (o function calling): la capacidad del modelo de, en lugar de responder directamente, decidir que necesita usar una herramienta externa —una búsqueda en internet, una consulta a una base de datos, el envío de un correo, una llamada a una API de pagos— y generar la instrucción estructurada (qué herramienta usar y con qué parámetros) para que el sistema que rodea al modelo la ejecute.

```{figure} ../_static/images/u2-tool-calling.jpg
:name: fig-u23-tool-calling
:alt: Ciclo de tool calling entre un modelo de lenguaje y una herramienta externa
:width: 85%

El ciclo de tool calling: el modelo decide qué herramienta necesita, el sistema la ejecuta, y el resultado vuelve al modelo para que continúe.
```



Es importante notar que el modelo de lenguaje nunca ejecuta la herramienta directamente — solo decide *que* hay que usarla y *con qué parámetros*; es el sistema que rodea al modelo (la aplicación o plataforma donde corre el agente) el que realmente hace la llamada a la API o a la base de datos, y le devuelve el resultado al modelo para que continúe razonando con esa información nueva. Esta separación es clave desde el punto de vista de negocio: permite controlar y auditar qué herramientas puede usar un agente y bajo qué condiciones, en lugar de darle acceso irrestricto a los sistemas de la organización.

Para hacerlo concreto: imaginemos un agente encargado de reprogramar citas médicas en una clínica. Un usuario escribe "necesito mover mi cita del jueves para la próxima semana". El agente no puede resolver esto solo con lenguaje: necesita (1) una herramienta para **consultar** la cita actual del paciente en el sistema de agendamiento, (2) una herramienta para **consultar** la disponibilidad de horarios la próxima semana, y (3) una herramienta para **confirmar** el cambio una vez el paciente elige un horario. El modelo de lenguaje decide, en cada paso, cuál de esas tres herramientas invocar y con qué parámetros (el ID del paciente, el rango de fechas a consultar, el horario elegido), pero quien realmente consulta o modifica la base de datos del sistema de agendamiento es el código que rodea al modelo — nunca el modelo mismo. Esto es, otra vez, una decisión de diseño con implicaciones de negocio: se puede decidir que las herramientas de "consultar" no requieren aprobación humana, pero que la de "confirmar un cambio" sí la requiera antes de ejecutarse, como medida de control.

## Sistemas multiagentes

Cuando una tarea es lo bastante compleja, a veces conviene no pedirle todo a un solo agente, sino dividir el trabajo entre varios agentes especializados que colaboran entre sí — un enfoque conocido como **sistema multiagente**. Por ejemplo, para automatizar la atención de solicitudes de un cliente, se podría tener un agente que clasifica la solicitud, otro que busca la información relevante en los sistemas internos, otro que redacta la respuesta, y un último que revisa que la respuesta cumpla las políticas de la empresa antes de enviarla — cada uno con un objetivo más acotado y, por tanto, más fácil de instruir bien y de supervisar.

```{figure} ../_static/images/u2-multiagentes.jpg
:name: fig-u23-multiagentes
:alt: Esquema de un sistema multiagente con un orquestador y agentes especializados
:width: 80%

Un sistema multiagente típico: un agente orquestador distribuye el trabajo entre agentes especializados.
```


La ventaja de dividir el trabajo así es que cada agente individual es más simple de diseñar, probar y corregir que un solo agente gigante que intente hacerlo todo; la desventaja es que se introduce complejidad de coordinación (qué agente habla primero, cómo se pasan información entre sí, qué pasa si uno falla), lo cual hace que diseñar bien un sistema multiagente sea, en sí mismo, un trabajo de ingeniería no trivial.

Un ejemplo que ayuda a visualizarlo es el de una empresa que quiere automatizar la elaboración de reportes de inteligencia de mercado sobre sus competidores. Un solo agente que tuviera que buscar información, analizarla, redactar el reporte y verificar que no haya errores tendría un prompt enorme y difícil de mantener, y cualquier falla sería difícil de rastrear a una causa concreta. Dividido en un sistema multiagente, se vería así: un **agente investigador** busca noticias, reportes financieros y movimientos recientes de los competidores; un **agente analista** organiza esa información cruda en hallazgos relevantes; un **agente redactor** convierte esos hallazgos en un reporte legible para un gerente; y un **agente revisor** verifica que las cifras citadas coincidan con las fuentes encontradas por el investigador, antes de que el reporte llegue a un humano. Si el reporte final tiene un error, es mucho más fácil ubicar en cuál de los cuatro agentes está el problema que si todo el proceso fuera responsabilidad de un agente monolítico.

## n8n: construyendo flujos con agentes sin programar desde cero

Todo lo anterior —prompting, tool calling, orquestación de varios agentes— se puede programar desde cero con código, pero también se puede construir usando plataformas no-code o low-code de automatización, siendo **n8n** una de las más usadas hoy. n8n permite armar flujos de trabajo visuales conectando "nodos" —un disparador (por ejemplo, que llegue un correo nuevo), nodos de lógica (condicionales, bucles), nodos que llaman modelos de IA, y nodos que ejecutan acciones (enviar un mensaje, escribir en una base de datos, llamar una API)— sin necesidad de escribir el código de integración entre cada pieza.

```{figure} ../_static/images/u2-n8n-flujo.jpg
:name: fig-u23-n8n-flujo
:alt: Ejemplo de un flujo visual construido en n8n con un nodo de agente de IA
:width: 85%

Un flujo típico en n8n: un disparador, un nodo de agente de IA con acceso a herramientas, y una acción final.
```



Esto conecta directamente con el criterio build vs. buy vs. adopt visto en la Unidad 1: para la gran mayoría de las organizaciones, especialmente las que no tienen un equipo de desarrollo dedicado, adoptar una plataforma como n8n para construir flujos con agentes es muchísimo más razonable que programar esa infraestructura desde cero — y permite que áreas de negocio (no solo IT) puedan participar directamente en el diseño de estos flujos.

Un ejemplo típico de flujo construido en n8n: una pyme recibe solicitudes de cotización por correo electrónico. El flujo se dispara cada vez que llega un correo nuevo a una bandeja específica; un nodo de agente de IA lee el correo y extrae los datos relevantes (producto solicitado, cantidad, datos de contacto); el agente usa una herramienta para consultar el catálogo de precios en una hoja de cálculo o base de datos; con esa información, genera una cotización en el formato de la empresa; y un último nodo envía esa cotización por correo al cliente, copiando al vendedor asignado para que haga seguimiento. Todo esto se construye arrastrando y conectando nodos en la interfaz visual de n8n, sin que nadie en la empresa tenga que escribir código de integración entre el correo, el agente de IA, la hoja de cálculo y el envío de la respuesta.

## Riesgos y límites de los agentes de IA

Así como es importante entender qué pueden hacer los agentes, es igual de importante entender dónde está su límite, porque delegarles autonomía sin entender estos riesgos es una fuente común de problemas en implementaciones reales:

- **Alucinaciones:** el modelo puede generar información que suena convincente pero es falsa — un agente que redacta un reporte puede inventar una cifra o una fuente si no se le obliga a basarse estrictamente en datos verificables obtenidos mediante tool calling.
- **Acciones irreversibles:** a diferencia de una respuesta de texto que se puede ignorar o corregir, una acción como enviar un pago, borrar un registro o enviar un correo a un cliente no se puede "deshacer" fácilmente — por eso las acciones de mayor riesgo suelen diseñarse con un paso de confirmación humana antes de ejecutarse.
- **Costo computacional y de latencia:** un agente que necesita varios pasos de razonamiento y varias llamadas a herramientas antes de completar una tarea es más lento y más costoso de operar que una respuesta directa de un modelo, lo cual debe pesarse contra el ahorro que genera automatizar la tarea.
- **Dependencia de la calidad de las herramientas e instrucciones:** un agente es tan bueno como las herramientas que tiene disponibles y las instrucciones (prompts) que lo gobiernan; un agente mal instruido con buenas herramientas puede ser tan problemático como uno bien instruido con herramientas defectuosas.

Por esto, la pregunta de negocio relevante no es "¿le damos autonomía total a un agente?", sino "¿en qué tareas, con qué nivel de supervisión, y con qué consecuencia si se equivoca?" — una versión más del tipo de análisis de riesgo que ya se ha visto en unidades anteriores del curso.

## Glosario de términos clave

**Prompt:** texto de entrada que se le da a un modelo de lenguaje para obtener una respuesta.

**Prompting (ingeniería de prompts):** la práctica de diseñar y afinar prompts para obtener resultados consistentes y útiles de un modelo de lenguaje.

**Chain-of-thought:** técnica de prompting que pide al modelo razonar paso a paso antes de dar una respuesta final.

**Agente de IA:** sistema construido sobre un modelo de lenguaje con autonomía para encadenar decisiones, mantener memoria de una tarea, y actuar sobre sistemas externos.

**Tool calling (function calling):** mecanismo por el cual un modelo decide que necesita usar una herramienta externa y genera la instrucción estructurada para invocarla.

**Sistema multiagente:** conjunto de varios agentes especializados que colaboran, normalmente coordinados por un agente orquestador, para resolver una tarea compleja.

**Agente orquestador:** agente responsable de distribuir el trabajo entre los demás agentes de un sistema multiagente y coordinar sus resultados.

**n8n:** plataforma no-code/low-code de automatización de flujos de trabajo, usada para construir procesos que integran agentes de IA, herramientas y sistemas externos sin programar desde cero.

**Alucinación:** respuesta generada por un modelo de lenguaje que suena convincente pero es factualmente incorrecta o inventada.

## Preguntas de repaso

1. Explica con tus palabras la diferencia entre un modelo de lenguaje al que se le hace una pregunta puntual, y un agente de IA construido sobre ese mismo modelo.
2. ¿Por qué el modelo de lenguaje nunca ejecuta directamente una herramienta en tool calling? ¿Qué ventaja de negocio tiene esa separación?
3. Describe una tarea de tu organización (la del proyecto final u otra que conozcas) que dividirías entre varios agentes especializados en lugar de dársela a un solo agente, y justifica por qué.
4. ¿Qué papel juega una plataforma como n8n en el criterio build vs. buy vs. adopt visto en la Unidad 1?
5. Menciona dos riesgos de darle autonomía a un agente de IA sin supervisión humana, y para cada uno propone una medida de control.

## Referencias de la sección

- Klarna (2024). *Klarna AI assistant handles two-thirds of service chats in its first month*. Comunicado de prensa corporativo.
- Davenport, T. H., & Ronanki, R. (2022). *The AI Advantage: How to Put the Artificial Intelligence Revolution to Work*. MIT Press.

```{admonition} Para tu proyecto final
:class: important
Para la organización elegida en tu proyecto final: describe un flujo de trabajo repetitivo que hoy se hace manualmente, y diseña (en papel o en n8n si quieres probarlo) cómo se vería automatizado con un agente de IA — qué disparador lo iniciaría, qué herramientas necesitaría el agente (tool calling), y si tendría sentido dividirlo entre varios agentes especializados o si uno solo bastaría.
```
