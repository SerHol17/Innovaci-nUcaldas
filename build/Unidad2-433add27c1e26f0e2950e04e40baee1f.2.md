---
title: Unidad 2.2 · Big Data y Analítica Avanzada
---

# Unidad 2.2 — Big Data y Analítica Avanzada para la Toma de Decisiones



```{admonition} Objetivo de la sección
:class: tip
Entender qué hace que un conjunto de datos sea "big data" y no simplemente "muchos datos", distinguir los niveles de madurez analítica de una organización, y conocer cómo se estructura la infraestructura de datos moderna (data warehouse, data lake, data lakehouse).
```

El término "big data" no se refiere simplemente a "muchos datos", sino a datos que por su volumen, velocidad de generación o variedad de formato dejan de poder manejarse cómodamente con las herramientas tradicionales (una hoja de cálculo, una sola máquina, un único formato tabular). El fenómeno no es nuevo, pero se ha vuelto central en la transformación digital porque cada proceso que se digitaliza —una venta, un clic, una lectura de sensor, una interacción en redes sociales— genera un rastro de datos que antes simplemente no existía.

## Las características del big data

Suele describirse el big data a través de tres características que, cuando se presentan juntas, exigen un cambio de herramientas y de enfoque:

- **Volumen:** la cantidad de datos generados es tan grande que ya no cabe cómodamente en la memoria de una sola máquina ni se procesa en un tiempo razonable con herramientas convencionales — se habla de terabytes o petabytes, no de megabytes.
- **Velocidad:** los datos se generan y necesitan procesarse a un ritmo muy alto, a veces en tiempo real o casi real — las transacciones de una pasarela de pagos, los datos de un sensor industrial, el flujo de clics en una aplicación.
- **Variedad:** los datos no vienen todos en un formato tabular limpio; incluyen texto libre, imágenes, audio, video, registros de log, datos geoespaciales, cada uno con su propia estructura (o ausencia de ella).

A estas tres se suele añadir una cuarta, más relacionada con la calidad que con el tamaño: la **veracidad**, es decir, qué tan confiables, completos y libres de error están los datos — un volumen enorme de datos poco confiables no resuelve ningún problema de negocio, y de hecho puede generar decisiones peores que no tener datos en absoluto.

## Los tres niveles de analítica

Independientemente del volumen de datos que maneje una organización, es útil distinguir tres niveles de analítica, porque cada uno responde una pregunta distinta y requiere un nivel de madurez de datos distinto:

- **Analítica descriptiva:** ¿qué pasó? Reportes, tableros, resúmenes de lo que ya ocurrió. Es el nivel en el que opera la mayoría de las organizaciones hoy: saber cuánto se vendió el mes pasado, cuántos clientes se perdieron, cuál fue el tiempo promedio de atención.
- **Analítica predictiva:** ¿qué va a pasar? Usa modelos de machine learning (como los vistos en la Unidad 2.1) para anticipar un resultado futuro a partir de patrones históricos.
- **Analítica prescriptiva:** ¿qué deberíamos hacer? Va un paso más allá de predecir, y recomienda una acción concreta considerando restricciones y objetivos de negocio — por ejemplo, no solo predecir la demanda de un producto, sino recomendar cuánto inventario pedir a cada bodega, considerando costos de transporte y capacidad de almacenamiento.

```{figure} ../_static/images/u2-bigdata-vs.jpg
:name: fig-u22-bigdata-vs
:alt: Los tres niveles de analítica de datos: descriptiva, predictiva y prescriptiva
:width: 80%

Los tres niveles de analítica, en orden creciente de madurez y de valor para la toma de decisiones.
```



La mayoría de las organizaciones todavía opera principalmente en analítica descriptiva. El salto a predictiva y prescriptiva es, en buena medida, lo que distingue a los perfiles "Digirati" del modelo del MIT visto en la Unidad 1: no es un problema de falta de datos, sino de falta de la infraestructura y las capacidades analíticas para aprovecharlos.

## De una sola máquina a un clúster: cómo se escala el análisis

Mientras el volumen de datos de una organización quepa cómodamente en una sola máquina (algunos millones de filas, un archivo que una herramienta como pandas en Python abre sin problema), el análisis se puede hacer con las herramientas convencionales de ciencia de datos. El problema aparece cuando ese volumen crece varios órdenes de magnitud —sensores IoT generando lecturas cada segundo, el historial transaccional completo de un banco, los registros de navegación de un sitio con millones de visitas diarias— o cuando los datos están distribuidos en muchos archivos o servidores distintos.

```{figure} ../_static/images/u2-escalamiento.jpg
:name: fig-u22-escalamiento
:alt: Comparación entre procesar datos en una sola máquina y distribuirlos en un clúster
:width: 80%

De una sola máquina a un clúster distribuido: la misma operación de análisis, repartida entre varios nodos que trabajan en paralelo.
```


En ese punto se recurre a herramientas como **Apache Spark**, que distribuye el procesamiento entre varias máquinas trabajando en paralelo: conceptualmente se siguen haciendo las mismas operaciones de siempre (agrupar, agregar, filtrar), pero la ejecución ocurre repartida en un clúster en lugar de en un solo proceso, lo que permite procesar en minutos un volumen de datos que a una sola máquina le tomaría días o que simplemente no le cabría en memoria. La decisión de cuándo pasar de pandas a Spark (o a una herramienta equivalente) es, otra vez, una decisión de negocio tanto como técnica: migrar a infraestructura distribuida tiene un costo de configuración y mantenimiento que solo se justifica cuando el volumen real de datos lo requiere.

## Arquitecturas de datos: dónde vive la información

Tan importante como la herramienta de procesamiento es la forma en que una organización almacena y organiza sus datos antes de analizarlos. Existen tres arquitecturas de referencia, que han evolucionado una sobre la otra:

- **Data warehouse (almacén de datos):** almacena datos ya estructurados y limpios, organizados específicamente para consultas analíticas y reportes. Es la arquitectura más madura y la más fácil de usar para analítica descriptiva, pero exige que los datos ya vengan en un formato tabular definido de antemano, lo que la hace poco flexible para datos no estructurados (texto, imágenes, logs).
- **Data lake (lago de datos):** almacena datos en su formato original (crudo), estructurados o no, sin exigir una estructura previa. Esto le da mucha flexibilidad y permite guardar prácticamente cualquier tipo de dato a bajo costo, pero a cambio es más difícil garantizar la calidad y consistencia de lo que hay ahí dentro — es fácil que un data lake termine siendo, en la práctica, un "data swamp" (pantano de datos) donde nadie sabe bien qué hay ni si es confiable.
- **Data lakehouse:** una arquitectura más reciente que busca combinar lo mejor de ambos mundos — la flexibilidad de almacenar cualquier tipo de dato crudo del data lake, con las garantías de estructura, calidad y gobernanza del data warehouse, típicamente mediante una capa adicional que organiza los datos crudos en niveles de calidad creciente (sin procesar, limpios, listos para negocio).

```{figure} ../_static/images/u2-arquitecturas-datos.jpg
:name: fig-u22-arquitecturas-datos
:alt: Comparación de las tres arquitecturas de datos: data warehouse, data lake y data lakehouse
:width: 85%

Las tres arquitecturas de datos de referencia y cómo evolucionó una sobre la otra.
```



La elección entre estas arquitecturas —o, como ocurre en la práctica, la coexistencia de varias de ellas dentro de la misma organización— es otra decisión que conecta directamente con el criterio build vs. buy vs. adopt de la Unidad 1: hoy existen servicios de data warehouse, data lake y data lakehouse completamente administrados por proveedores de nube, lo que reduce significativamente la necesidad de construir esta infraestructura desde cero.

## Gobernanza y calidad de datos

Ninguna arquitectura ni herramienta de analítica compensa datos de mala calidad. La gobernanza de datos —las políticas, roles y procesos que definen quién puede acceder a qué datos, cómo se garantiza su calidad, y cómo se documenta su origen (linaje)— se vuelve crítica a medida que una organización integra más fuentes de datos distintas, porque el riesgo de inconsistencias, duplicados y datos desactualizados crece con cada fuente nueva. Una organización que avanza en analítica predictiva o prescriptiva sin haber resuelto primero la calidad y gobernanza de sus datos corre el riesgo de automatizar decisiones equivocadas más rápido de lo que las tomaría un humano.

```{admonition} Para tu proyecto final
:class: important
Para la organización elegida en tu proyecto final: identifica en qué nivel de analítica está hoy (descriptiva, predictiva o prescriptiva), qué arquitectura de datos usa o debería usar (warehouse, lake o lakehouse), y si el volumen actual de sus datos realmente justificaría herramientas de procesamiento distribuido como Spark, o si las herramientas convencionales todavía le bastan.
```
