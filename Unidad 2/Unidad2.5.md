---
title: Unidad 2.5 · Cloud Computing e Infraestructura Digital
---

# Unidad 2.5 — Cloud Computing e Infraestructura Digital

```{admonition} Objetivo de la sección
:class: tip
Entender qué significa realmente "la nube" más allá del marketing, distinguir los tres modelos de servicio (IaaS, PaaS, SaaS) y cuándo conviene cada uno, conocer los modelos de despliegue (pública, privada, híbrida, multi-nube) y los criterios reales —no solo de costo— para decidir si migrar o no a la nube.
```

En la Unidad 2 se introdujo el cloud computing como el acceso a recursos de cómputo —servidores, almacenamiento, bases de datos, redes— como un servicio a través de internet, pagando por uso, en lugar de comprar y mantener infraestructura física propia. Esta sección desarrolla en detalle los modelos de servicio, los modelos de despliegue, y sobre todo el criterio de decisión que una organización debería usar antes de migrar algo a la nube, porque "migrar a la nube" dejó de ser una pregunta de sí o no hace años, y se volvió una pregunta de **qué, cómo y bajo qué modelo**.

## Los tres modelos de servicio: IaaS, PaaS, SaaS

La diferencia entre estos tres modelos no es cosmética: define cuánta responsabilidad técnica asume la organización frente a cuánta asume el proveedor, y por tanto qué tan rápido se puede desplegar algo y qué tanto control se conserva sobre él.

- **IaaS (Infraestructura como Servicio):** el proveedor entrega los recursos más básicos de cómputo —servidores virtuales, almacenamiento en bloque, redes virtuales— y la organización es responsable de instalar y administrar desde el sistema operativo hacia arriba (parches, configuración, seguridad del sistema operativo, el software que corre encima). Es el nivel de menor gestión por parte del proveedor y, por tanto, el de mayor flexibilidad pero también mayor carga operativa. Ejemplos: Amazon EC2, Azure Virtual Machines, Google Compute Engine.
- **PaaS (Plataforma como Servicio):** el proveedor gestiona además el sistema operativo, el entorno de ejecución y buena parte de la infraestructura subyacente (balanceo de carga, escalamiento automático), y la organización solo se preocupa por desplegar y mantener su propia aplicación. Es el punto intermedio: se gana velocidad de desarrollo a cambio de perder algo de control de bajo nivel. Ejemplos: Heroku, Azure App Service, Google App Engine.
- **SaaS (Software como Servicio):** el proveedor entrega una aplicación completa, lista para usar, y la organización solo la consume (normalmente pagando una suscripción). Es la categoría que ya se trabajó en la Unidad 1 dentro del criterio "adopt". Ejemplos: Salesforce, Microsoft 365, Google Workspace.

```{figure} ../_static/images/u25-modelos-servicio.jpg
:name: fig-u25-modelos-servicio
:alt: Los tres modelos de servicio en la nube y qué capa gestiona cada parte
:width: 85%

De IaaS a SaaS, la porción de la pila tecnológica que gestiona el proveedor crece, y la que gestiona la organización se reduce.
```



Una forma útil de hacer tangible esta diferencia para un equipo de negocio es la analogía de "¿quién cocina la pizza?": en IaaS la organización recibe la cocina equipada (horno, ingredientes crudos) y tiene que cocinar todo; en PaaS recibe la masa ya preparada y solo agrega sus ingredientes; en SaaS simplemente pide la pizza ya hecha. Ninguna opción es "mejor" en abstracto — depende de cuánto control necesita la organización sobre el resultado final, y cuánta capacidad técnica tiene disponible para ejercer ese control.

## Modelos de despliegue: pública, privada, híbrida y multi-nube

Independientemente del modelo de servicio, existe otra decisión ortogonal: dónde físicamente corre esa infraestructura y quién la comparte.

- **Nube pública:** la infraestructura es propiedad de un proveedor externo (AWS, Azure, GCP) y se comparte entre múltiples clientes (aislados lógicamente entre sí), lo que permite economías de escala y un costo mucho menor que operar infraestructura propia.
- **Nube privada:** la infraestructura está dedicada a una sola organización, ya sea alojada en sus propias instalaciones o gestionada por un tercero pero sin compartirse con otros clientes. Se usa cuando existen requisitos regulatorios estrictos (por ejemplo, datos de salud o financieros que no pueden salir de una jurisdicción específica) o necesidades de rendimiento muy particulares.
- **Nube híbrida:** combina infraestructura propia (o privada) con nube pública, con cargas de trabajo que se mueven entre ambas según convenga — por ejemplo, mantener los datos sensibles en infraestructura propia pero usar la nube pública para picos de demanda estacional.
- **Multi-nube:** la organización usa simultáneamente más de un proveedor de nube pública (por ejemplo, AWS para unas cargas y Azure para otras), normalmente para evitar depender de un único proveedor (*vendor lock-in*) o para aprovechar fortalezas específicas de cada uno.

```{figure} ../_static/images/u25-modelos-despliegue.jpg
:name: fig-u25-modelos-despliegue
:alt: Los cuatro modelos de despliegue en la nube: pública, privada, híbrida y multi-nube
:width: 85%

Los cuatro modelos de despliegue, según dónde corre la infraestructura y con quién se comparte.
```



## ¿Por qué migrar a la nube? Más allá del ahorro de costos

El argumento de venta más común para la nube es el ahorro de costos, pero reducir la decisión solo a eso es un error de análisis frecuente, porque en algunos escenarios de uso intensivo y constante la nube pública puede terminar costando más a largo plazo que mantener infraestructura propia. Los beneficios que realmente suelen inclinar la balanza son otros:

- **Elasticidad:** la capacidad de escalar recursos hacia arriba o hacia abajo en minutos según la demanda real, en lugar de comprar capacidad fija dimensionada para el peor escenario (el pico de ventas de diciembre, por ejemplo) y dejarla subutilizada el resto del año.
- **Velocidad de innovación:** levantar un nuevo servicio o probar una idea toma minutos en la nube, frente a semanas o meses de adquisición y configuración de infraestructura física — lo cual es determinante para la capacidad de una organización de experimentar y adaptarse rápido, un tema central de la Unidad 1.
- **Acceso a servicios gestionados avanzados:** bases de datos administradas, servicios de inteligencia artificial preentrenados, infraestructura de big data (como Spark gestionado), todos disponibles como servicio sin que la organización tenga que operar esa infraestructura especializada internamente — otra manifestación del criterio "adopt" aplicado a infraestructura, no solo a aplicaciones.
- **Resiliencia y continuidad del negocio:** los proveedores de nube ofrecen redundancia geográfica y mecanismos de recuperación ante desastres que serían extremadamente costosos de replicar por cuenta propia para la mayoría de las organizaciones.

Y el riesgo que con más frecuencia se subestima:

- **Vendor lock-in (dependencia del proveedor):** cuanto más se usan los servicios propietarios avanzados de un proveedor específico, más costoso y complejo se vuelve migrar después a otro proveedor o de vuelta a infraestructura propia — una decisión de arquitectura temprana que vale la pena discutir explícitamente, no asumir por defecto.

```{admonition} Criterio de decisión, no solo de costo
:class: warning
Antes de migrar una carga de trabajo a la nube, la pregunta relevante no es únicamente "¿es más barato?", sino: ¿necesitamos elasticidad real (la demanda varía significativamente)?, ¿qué tan crítico es mantener control total sobre dónde viven los datos por razones regulatorias?, ¿cuánto nos ata el uso de servicios propietarios de un proveedor específico a futuro? Una carga de trabajo con demanda constante y predecible, sin restricciones regulatorias, puede no beneficiarse tanto de la nube como una con demanda variable o estacional.
```

## La capa gratuita: el primer contacto real con infraestructura en la nube

Los tres proveedores dominantes del mercado —Amazon Web Services (AWS), Microsoft Azure y Google Cloud Platform (GCP)— ofrecen todos una capa gratuita limitada, pensada para que una organización (o un estudiante) tenga su primer contacto real con infraestructura en la nube sin incurrir en costos: subir y descargar archivos de un servicio de almacenamiento como Amazon S3 o Azure Blob Storage, levantar una máquina virtual pequeña, desplegar una base de datos administrada de bajo volumen, o correr funciones serverless con un número limitado de invocaciones al mes, todo dentro de los límites de la capa gratuita de cada proveedor.

Esto conecta directamente con los laboratorios prácticos de esta unidad: el notebook de big data de la sección 2.2 corre sobre Google Colab, que en el fondo es una forma de cómputo en la nube gestionado por Google con una capa gratuita generosa — el mismo principio de "acceder a cómputo como servicio sin comprar infraestructura propia" que se está discutiendo aquí a nivel conceptual.

## Glosario de términos clave

**Cloud computing (computación en la nube):** acceso a recursos de cómputo como servicio a través de internet, pagando por uso, sin poseer ni operar la infraestructura física.

**IaaS (Infraestructura como Servicio):** modelo de servicio en la nube donde el proveedor entrega los recursos básicos de cómputo y la organización gestiona desde el sistema operativo hacia arriba.

**PaaS (Plataforma como Servicio):** modelo de servicio en la nube donde el proveedor gestiona también el sistema operativo y el entorno de ejecución, y la organización solo despliega su aplicación.

**SaaS (Software como Servicio):** modelo de servicio en la nube donde el proveedor entrega una aplicación completa lista para usar.

**Nube pública:** infraestructura de un proveedor externo, compartida lógicamente entre múltiples clientes.

**Nube privada:** infraestructura dedicada exclusivamente a una sola organización.

**Nube híbrida:** combinación de infraestructura propia o privada con nube pública.

**Multi-nube:** uso simultáneo de más de un proveedor de nube pública.

**Elasticidad:** capacidad de escalar recursos de cómputo hacia arriba o hacia abajo rápidamente según la demanda real.

**Vendor lock-in:** dependencia creciente de los servicios propietarios de un proveedor específico, que dificulta migrar a otro proveedor en el futuro.

## Preguntas de repaso

1. Usando la analogía de la pizza (o una propia), explica la diferencia entre IaaS, PaaS y SaaS en términos de qué gestiona el proveedor y qué gestiona la organización.
2. ¿En qué escenario elegirías una nube privada o híbrida en lugar de una nube pública completa? Da un ejemplo concreto de sector o tipo de dato.
3. ¿Por qué reducir la decisión de migrar a la nube únicamente al ahorro de costos es un error de análisis? Menciona al menos dos beneficios adicionales.
4. Explica qué es el vendor lock-in y propone una estrategia (aunque sea parcial) para mitigarlo.
5. Retoma el marco build vs. buy vs. adopt de la Unidad 1 y clasifica cada uno de los tres modelos de servicio (IaaS, PaaS, SaaS) según qué tanto se parece a "build" y qué tanto a "adopt".

## Referencias de la sección

- Armbrust, M., et al. (2010). *A View of Cloud Computing*. Communications of the ACM.
- Wade, M., & Shan, J. (2023). *Hacking Digital: Best Practices to Implement and Accelerate Your Business Transformation*. McGraw-Hill Education.
- Amazon Web Services, Microsoft Azure, Google Cloud Platform. Documentación oficial de modelos de servicio y capas gratuitas (consultada en 2026).

```{admonition} Para tu proyecto final
:class: important
Para la organización elegida en tu proyecto final: identifica un proceso o sistema que hoy corre en infraestructura propia. Aplica el "criterio de decisión" de esta sección (elasticidad de la demanda, restricciones regulatorias, riesgo de vendor lock-in) para argumentar si migrarlo a la nube tendría sentido, y bajo qué modelo de servicio (IaaS, PaaS o SaaS) y de despliegue (pública, privada, híbrida).
```
