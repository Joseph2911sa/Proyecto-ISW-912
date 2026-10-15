# Plataforma de Registro Individual de Ganado

## Sección 00 — Portada e identificación del equipo

**Proyecto final — ISW-912 · Administración de Proyectos Informáticos**
Universidad Técnica Nacional · Sede Regional de San Carlos · II Cuatrimestre 2026

**Estudiantes:** Marco López Quesada · Joseph Salazar Araya
**Profesor:** Deiver Cubero Molina

### Definición del Scrum Team

| Rol | Integrante | Responsabilidades principales |
|---|---|---|
| Product Owner | Marco López Quesada | Define y prioriza el Product Backlog; representa la visión del producto y las necesidades de los productores; decide qué se construye en cada Sprint. |
| Scrum Master | Joseph Salazar Araya | Facilita el proceso Scrum; da seguimiento al Sprint Backlog; elimina obstáculos del equipo; organiza Sprint Planning, Daily Scrum, Sprint Review y Retrospective. |
| Developers | Marco López Quesada y Joseph Salazar Araya | Diseñan, construyen, prueban e integran la solución técnica: modelo de datos, interfaz y módulo de IA/OCR. |

Duración del equipo: 14 semanas, correspondientes a la duración completa del curso.

---

## Sección 01 — Problema, oportunidad y Product Goal

### Acta de Inicio (Project Charter)

#### Justificación del proyecto

En Costa Rica, el sistema nacional de trazabilidad Trazar-Agro está enfocado casi
exclusivamente en el cumplimiento sanitario y comercial del ganado bovino y porcino, sin
ofrecer a los productores —en particular a los pequeños y medianos, muchos de ellos
adultos mayores con poca familiaridad tecnológica— una herramienta de uso interno para
administrar el historial detallado de cada animal (salud, peso, reproducción,
fotografías, propietario). El registro manual del número de arete es, además, propenso a
errores de digitación, y la conectividad en las fincas rurales suele ser limitada.

El proyecto se justifica porque complementa, sin duplicar, el sistema oficial: ofrece a
los productores una plataforma propia para el control individual de su ganado, con una
interfaz simplificada y un módulo de inteligencia artificial que agiliza el registro
mediante fotografía (lectura del arete, sugerencia de raza y color/patrón), reduciendo el
tiempo y los errores de digitación, especialmente para usuarios con menor destreza
tecnológica.

#### Objetivo general

Desarrollar una plataforma digital que permita el registro y control individual detallado
del ganado en Costa Rica, organizado por categorías de especie y asociado a un propietario
mediante cédula, con generación automática de código único por animal y un módulo de IA
que agilice el registro mediante fotografía.

#### Objetivos específicos

1. Diseñar el modelo de datos multi-especie (bovinos, porcinos, equinos, etc.), incluyendo
   la entidad Propietario (cédula física o jurídica) vinculada a uno o varios animales,
   ficha detallada por animal, foto opcional y generación automática de código único.
2. Implementar un módulo de asistencia por IA que, a partir de la foto del animal,
   extraiga el número de arete mediante OCR cuando exista (usándolo como referencia si el
   animal ya está registrado oficialmente, o como base para iniciar su ficha si no lo
   está), y sugiera raza y color/patrón de pelaje como apoyo al llenado, con corrección
   manual en todos los casos.
3. Diseñar y validar una interfaz de uso simple (pasos guiados, mínima digitación) con
   productores reales o simulados, priorizando la accesibilidad para usuarios adultos
   mayores con poca experiencia en plataformas digitales.

#### Límites generales del proyecto

**Dentro del alcance**

- Registro y gestión de fichas individuales de ganado multi-especie (bovino, porcino,
  equino, etc.).
- Asociación de animales a un propietario mediante cédula física o jurídica.
- Generación automática de código único por animal.
- Módulo de IA/OCR para lectura de arete y sugerencia de raza/color-patrón a partir de
  fotografía.
- Interfaz simplificada orientada a productores con baja alfabetización digital.

**Fuera del alcance**

- Sustitución o duplicación del registro oficial de Trazar-Agro/SENASA.
- Procesos de pago, facturación o comercialización de ganado.
- Módulo veterinario avanzado (diagnósticos, historiales clínicos detallados) en esta
  fase.
- Soporte completamente offline; se asume conectividad intermitente, no ausencia total de
  red.
- Equipo de desarrollo de 2 integrantes, trabajo acotado a las 14 semanas del curso.

### Product Goal

Una plataforma digital de registro y control individual detallado del ganado en Costa
Rica, organizada por categorías de especie, con cada animal asociado a un propietario
mediante cédula, código único generado automáticamente y un módulo de IA que agilice el
registro mediante fotografía.

---

## Sección 02 — Contexto organizacional y restricciones

### Lean Canvas

| Bloque | Contenido |
|---|---|
| Problema | Falta de una herramienta interna, simple y detallada para el control individual del ganado; Trazar-Agro cubre solo trazabilidad sanitaria/comercial; alta tasa de error en digitación manual del arete. |
| Segmentos de clientes | Productores pequeños y medianos; productores adultos mayores; propietarios con varias especies en una misma finca. |
| Propuesta de valor única | Control individual y detallado del ganado, con registro asistido por IA que reduce tiempo y errores de digitación, complementando el sistema nacional sin duplicarlo. |
| Solución | Plataforma multi-especie con ficha por animal, código único, asociación a propietario por cédula y módulo de IA/OCR para lectura de arete y sugerencia de raza/color-patrón. |
| Canales | Aplicación web/móvil; difusión a través de cooperativas y asociaciones de productores agropecuarios. |
| Flujos de ingreso | Proyecto académico, sin modelo de ingresos definido en esta etapa. |
| Estructura de costos | Tiempo de desarrollo del equipo (2 estudiantes); hosting; costo de servicios de OCR/IA en la nube. |
| Métricas clave | Número de animales registrados; tasa de precisión del OCR; tasa de adopción en pruebas con usuarios reales o simulados. |
| Ventaja injusta | Diseño construido específicamente para el contexto costarricense (conectividad limitada, usuarios adultos mayores) e integración conceptual con Trazar-Agro/SENASA. |

### Factores Ambientales de la Empresa (EEF)

**Internos**

- Equipo de 2 desarrolladores (Marco y Joseph), sin estructura jerárquica formal; las
  decisiones se toman en conjunto.
- Tiempo disponible limitado al calendario académico de 14 semanas.
- Presupuesto estudiantil, dependiente de servicios gratuitos o de bajo costo (APIs de
  OCR, hosting).

**Externos**

- Normativa y sistema nacional Trazar-Agro / SENASA: cambios en sus políticas de datos o
  de acceso pueden afectar la integración planteada.
- Conectividad rural limitada en muchas fincas costarricenses.
- Perfil demográfico del usuario final (productores adultos mayores, baja alfabetización
  digital), que condiciona el diseño de la interfaz.
- Disponibilidad y costo de servicios de IA/OCR en la nube (dependencia de terceros).
- Normativa de protección de datos personales (cédula del propietario) aplicable en Costa
  Rica.

### Tipo de estructura organizacional

Orientada a proyectos: equipo de 2 integrantes, sin estructura jerárquica formal; las
decisiones se toman en conjunto.

### Restricciones

- Equipo de desarrollo de 2 integrantes, trabajo acotado a las 14 semanas del curso.
- Presupuesto estudiantil, dependiente de servicios gratuitos o de bajo costo (APIs de
  OCR, hosting).
- Conectividad rural limitada en muchas fincas costarricenses.
- Perfil demográfico del usuario final (productores adultos mayores, baja alfabetización
  digital), que condiciona el diseño de la interfaz.
- El proyecto complementa, sin duplicar, el sistema oficial.

---

## Sección 03 — Interesados / stakeholders

### Registro de interesados

| Interesado | Rol / relación | Necesidad | Poder (1-5) | Interés (1-5) | Actitud | Estrategia | Responsable |
|---|---|---|---|---|---|---|---|
| Productores pequeños/medianos | Usuarios principales | Control simple y rápido de su ganado | 2 | 5 | Favorable | Informar y validar la interfaz con ellos | Marco López Quesada |
| Productores adultos mayores | Segmento crítico de usuarios | Interfaz sencilla, mínima digitación | 2 | 5 | Mixta | Involucrar en pruebas de usabilidad tempranas | Marco López Quesada |
| SENASA / Trazar-Agro | Entidad reguladora / sistema nacional | Que el proyecto no duplique ni interfiera con el registro oficial | 5 | 3 | Neutral | Mantener informado; diseñar como complemento | Joseph Salazar Araya |
| Equipo desarrollador | Responsables del proyecto | Cumplir los objetivos del curso y del producto | 5 | 5 | Favorable | Gestionar de cerca | Marco López Quesada y Joseph Salazar Araya |
| Profesor del curso | Evaluador / patrocinador académico | Evidencia de aplicación correcta de los conceptos del curso | 4 | 4 | Favorable | Mantener informado con avances semanales | Joseph Salazar Araya |
| Proveedor de servicio OCR/IA | Tercero tecnológico | Uso correcto de su API/servicio | 2 | 2 | Neutral | Monitorear disponibilidad y costos | Joseph Salazar Araya |
| Cooperativas y asociaciones de productores | Canal de difusión entre productores | Que la herramienta sea útil para sus asociados y fácil de recomendar | 3 | 4 | Favorable | Mantener informado y consultar sobre la difusión | Marco López Quesada |
| Médicos veterinarios y asistentes técnicos | Usuarios secundarios; apoyo a los productores | Consultar con claridad los datos individuales de cada animal | 2 | 3 | Neutral | Monitorear y considerar su opinión sobre los datos de la ficha | Marco López Quesada |
| Entidad de protección de datos personales | Entidad reguladora | Que el manejo de la cédula del propietario cumpla la normativa | 4 | 2 | Neutral | Mantener satisfecho; aplicar la normativa en el diseño de los datos | Joseph Salazar Araya |

### Justificación de las valoraciones discutibles

- **SENASA / Trazar-Agro (poder 5, interés 3):** su normativa y su sistema oficial pueden
  condicionar el diseño del producto, por eso el poder es alto; el interés es moderado
  porque la plataforma es una herramienta de uso interno del productor que complementa el
  sistema oficial y no sustituye ningún trámite.
- **Productores adultos mayores (poder 2, actitud mixta):** su poder de decisión sobre el
  proyecto es bajo, pero de su adopción depende el cumplimiento del tercer objetivo
  específico; la actitud es mixta por su poca familiaridad con plataformas digitales.
- **Cooperativas y asociaciones de productores (poder 3, interés 4):** no deciden el alcance
  del producto, pero pueden facilitar o dificultar su difusión entre los asociados.
- **Entidad de protección de datos personales (poder 4, interés 2):** puede exigir el
  cumplimiento de la normativa sobre la cédula del propietario, pero no sigue de cerca el
  avance del proyecto.

### Mapa Poder-Interés

```mermaid
quadrantChart
    title Mapa Poder-Interes
    x-axis Bajo Interes --> Alto Interes
    y-axis Bajo Poder --> Alto Poder
    quadrant-1 Gestionar de cerca
    quadrant-2 Mantener satisfecho
    quadrant-3 Monitorear
    quadrant-4 Mantener informado
    Productores pequenos/medianos: [0.85, 0.35]
    Productores adultos mayores: [0.85, 0.30]
    SENASA / Trazar-Agro: [0.45, 0.85]
    Equipo desarrollador: [0.9, 0.9]
    Profesor del curso: [0.65, 0.7]
    Proveedor OCR/IA: [0.25, 0.3]
    Cooperativas y asociaciones: [0.65, 0.48]
    Medicos veterinarios: [0.45, 0.30]
    Entidad de proteccion de datos: [0.25, 0.70]
```

### Interesados críticos

| Interesado crítico | Por qué es crítico | Forma de involucramiento |
|---|---|---|
| Productores adultos mayores | De su adopción depende el cumplimiento del tercer objetivo específico y es el segmento con menor familiaridad tecnológica. | Pruebas de usabilidad tempranas del registro guiado con productores reales o simulados; sus observaciones se incorporan al Product Backlog y se revisan al cierre de cada Sprint. |
| SENASA / Trazar-Agro | Su normativa y su sistema oficial determinan que el producto sea un complemento y no un duplicado del registro oficial. | Consulta de su información pública al definir cada Sprint, para confirmar que el alcance complementa el registro oficial sin duplicarlo. |
| Profesor del curso | Evalúa cada entrega del Expediente, del repositorio y de la demostración. | Avance semanal del Expediente y del repositorio, y atención de su retroalimentación en el Sprint siguiente. |

---

## Sección 04 — Ciclo de vida del proyecto y primer Sprint

### Ciclo de vida del proyecto

El proyecto nace del problema descrito en la Sección 01: el sistema nacional Trazar-Agro
cubre el cumplimiento sanitario y comercial, pero los productores no cuentan con una
herramienta propia, detallada y fácil de usar para el control individual de cada animal.

La fecha de la entrega oficial es fija (Semana 11) y el alcance se construye de forma
adaptativa mediante 5 Sprints de 2 semanas, por lo que el ciclo de vida del proyecto es
híbrido.

El trabajo avanza por tres líneas, tomadas de los objetivos específicos:

1. Modelo de datos y registro individual: modelo multi-especie, propietario por cédula,
   ficha por animal y código único.
2. Módulo de asistencia por IA: lectura del arete mediante OCR y sugerencia de raza y
   color/patrón, con corrección manual.
3. Interfaz simple y validación: pasos guiados y mínima digitación, validados con
   productores reales o simulados.

El cierre del proyecto consiste en la entrega oficial del Expediente completo, la
demostración del incremento y la defensa ante el docente en la Semana 11.

### Primer Sprint

**Duración:** 2 semanas (Sprint 1 de 5).

**Sprint Goal:** Permitir al productor registrar un animal asociado a un propietario
identificado por cédula, con su código único generado automáticamente, y consultar su
ficha. Todo lo demás queda para futuros Sprints.

**Historias que se atacan primero**

- HU-01 Registro de propietario por cédula.
- HU-02 Registro de animal asociado a un propietario.
- HU-03 Código único por animal.
- HU-04 Consulta de la ficha del animal.

**Por qué estas historias:** son la base de la que dependen las demás. Sin propietario y
animal registrados no hay a qué asociar la fotografía, la lectura del arete ni las
sugerencias del módulo de IA.

---

## Sección 05 — Backlog inicial y Sprint Backlog

### Backlog inicial

El backlog está ordenado por valor para el productor y por dependencia entre historias.

| ID | Historia de usuario | Prioridad |
|---|---|---|
| HU-01 | Como productor, quiero registrar a un propietario por su cédula física o jurídica para asociarle sus animales. | Alta |
| HU-02 | Como productor, quiero registrar un animal en su categoría de especie, asociado a un propietario, para llevar su control individual. | Alta |
| HU-03 | Como productor, quiero que cada animal reciba un código único generado automáticamente para identificarlo sin duplicados. | Alta |
| HU-04 | Como productor, quiero consultar la ficha de un animal registrado para ver sus datos. | Alta |
| HU-05 | Como productor, quiero administrar varios animales de un mismo propietario desde una sola cuenta. | Media |
| HU-06 | Como productor, quiero completar la ficha detallada del animal con su salud, peso y reproducción. | Media |
| HU-07 | Como productor, quiero adjuntar una fotografía opcional del animal. | Media |
| HU-08 | Como productor, quiero que la plataforma lea el número de arete a partir de la fotografía (OCR) para reducir errores de digitación. | Media |
| HU-09 | Como productor, quiero recibir sugerencias de raza y de color/patrón de pelaje a partir de la fotografía para completar la ficha con menos esfuerzo. | Media |
| HU-10 | Como productor, quiero corregir manualmente los datos sugeridos por el módulo de IA. | Media |
| HU-11 | Como productor, quiero registrar un animal mediante pasos guiados y con mínima digitación. | Media |
| HU-12 | Como productor, quiero que, si el animal ya está registrado oficialmente, el número de arete se use como referencia para complementar su ficha sin duplicar el registro oficial. | Media |

### Sprint Backlog del primer Sprint

**Sprint Goal:** Permitir al productor registrar un animal asociado a un propietario
identificado por cédula, con su código único generado automáticamente, y consultar su
ficha.

| Historia | Plan de entrega |
|---|---|
| HU-01 | Definir los datos del propietario (cédula física o jurídica) y su registro. |
| HU-02 | Definir la ficha del animal por categoría de especie y su registro asociado a un propietario. |
| HU-03 | Definir la regla de generación automática del código único. |
| HU-04 | Mostrar la ficha del animal registrado con sus datos. |

### Mecanismo de seguimiento

El Sprint Backlog se sigue en un tablero con las columnas Por hacer, En curso y Hecho, que
se actualiza en un Daily Scrum breve. El Scrum Master organiza el Daily Scrum y da
seguimiento al Sprint Backlog.

---

## Sección 06 — Alcance, Product Backlog priorizado y criterios de aceptación

### Declaración de alcance

El alcance incluye el registro y control individual del ganado multi-especie, la asociación
de cada animal a un propietario mediante cédula, la generación automática del código único
y el módulo de IA/OCR para la lectura del arete y la sugerencia de raza y color/patrón.
Excluye la sustitución o duplicación del registro oficial de Trazar-Agro/SENASA. Los
límites generales del proyecto se detallan en la Sección 01.

### Product Backlog priorizado

El orden refleja el valor para el productor y la dependencia entre historias. La
estimación se expresa en puntos de historia (secuencia de Fibonacci).

| Orden | ID | Historia | Prioridad | Estimación (puntos) |
|---|---|---|---|---|
| 1 | HU-01 | Registro de propietario por cédula | Alta | 3 |
| 2 | HU-02 | Registro de animal asociado a un propietario | Alta | 5 |
| 3 | HU-03 | Código único por animal | Alta | 3 |
| 4 | HU-04 | Consulta de la ficha del animal | Alta | 3 |
| 5 | HU-05 | Varios animales por propietario | Media | 3 |
| 6 | HU-06 | Ficha detallada del animal | Media | 8 |
| 7 | HU-07 | Fotografía opcional del animal | Media | 3 |
| 8 | HU-08 | Lectura del número de arete (OCR) | Media | 8 |
| 9 | HU-09 | Sugerencia de raza y color/patrón | Media | 8 |
| 10 | HU-10 | Corrección manual de lo sugerido por la IA | Media | 3 |
| 11 | HU-11 | Registro guiado con mínima digitación | Media | 5 |
| 12 | HU-12 | Arete como referencia del registro oficial | Media | 5 |

### Criterios de aceptación

#### HU-01 — Registro de propietario por cédula

**Como** productor, **quiero** registrar a un propietario por su cédula física o jurídica
**para** asociarle sus animales.

**Prioridad:** Alta · **Estimación:** 3 puntos

1. *Dado que* el productor ingresa una cédula física o jurídica que no está registrada,
   *cuando* guarda el propietario, *entonces* el sistema crea el registro del propietario.
2. *Dado que* ya existe un propietario con esa cédula, *cuando* el productor intenta
   registrarlo de nuevo, *entonces* el sistema no crea un duplicado e informa que ya está
   registrado.
3. *Dado que* el productor no ingresa la cédula, *cuando* intenta guardar, *entonces* el
   sistema no registra al propietario y solicita completar el dato.

#### HU-02 — Registro de animal asociado a un propietario

**Como** productor, **quiero** registrar un animal en su categoría de especie, asociado a
un propietario, **para** llevar su control individual.

**Prioridad:** Alta · **Estimación:** 5 puntos

1. *Dado que* existe un propietario registrado, *cuando* el productor registra un animal
   indicando su categoría de especie y el propietario, *entonces* el animal queda
   registrado y asociado a ese propietario.
2. *Dado que* falta la especie o el propietario, *cuando* el productor intenta guardar,
   *entonces* el sistema no registra el animal y señala el dato faltante.

#### HU-03 — Código único por animal

**Como** productor, **quiero** que cada animal reciba un código único generado
automáticamente **para** identificarlo sin duplicados.

**Prioridad:** Alta · **Estimación:** 3 puntos

1. *Dado que* se registra un animal, *cuando* se guarda, *entonces* el sistema le asigna
   un código único generado automáticamente.
2. *Dado que* ya existen animales con código asignado, *cuando* se registra otro animal,
   *entonces* su código es distinto de todos los existentes.

#### HU-04 — Consulta de la ficha del animal

**Como** productor, **quiero** consultar la ficha de un animal registrado **para** ver sus
datos.

**Prioridad:** Alta · **Estimación:** 3 puntos

1. *Dado que* el animal está registrado, *cuando* el productor consulta su ficha,
   *entonces* el sistema muestra su código único, su especie y su propietario.

#### HU-05 — Varios animales por propietario

**Como** productor, **quiero** administrar varios animales de un mismo propietario desde
una sola cuenta **para** llevar el control de todo su ganado en un solo lugar.

**Prioridad:** Media · **Estimación:** 3 puntos

1. *Dado que* un propietario tiene animales registrados, *cuando* el productor consulta a
   ese propietario, *entonces* el sistema muestra la lista de todos sus animales.
2. *Dado que* el productor registra otro animal para el mismo propietario, *cuando* lo
   guarda, *entonces* el animal aparece en la lista junto con los anteriores.

#### HU-06 — Ficha detallada del animal

**Como** productor, **quiero** completar la ficha detallada del animal con su salud, peso
y reproducción **para** llevar el historial de cada animal.

**Prioridad:** Media · **Estimación:** 8 puntos

1. *Dado que* el animal está registrado, *cuando* el productor completa datos de salud,
   peso o reproducción y guarda, *entonces* la ficha conserva esos datos.
2. *Dado que* la ficha tiene datos de salud, peso o reproducción, *cuando* el productor la
   consulta, *entonces* el sistema los muestra junto con los datos básicos del animal.

#### HU-07 — Fotografía opcional del animal

**Como** productor, **quiero** adjuntar una fotografía opcional del animal **para**
identificarlo visualmente en su ficha.

**Prioridad:** Media · **Estimación:** 3 puntos

1. *Dado que* el productor registra un animal, *cuando* no adjunta fotografía, *entonces*
   el registro se completa sin ella.
2. *Dado que* el productor adjunta una fotografía, *cuando* guarda el registro, *entonces*
   la fotografía queda asociada a la ficha y se muestra al consultarla.

#### HU-08 — Lectura del número de arete (OCR)

**Como** productor, **quiero** que la plataforma lea el número de arete a partir de la
fotografía (OCR) **para** reducir errores de digitación.

**Prioridad:** Media · **Estimación:** 8 puntos

1. *Dado que* la fotografía muestra un arete legible, *cuando* el productor solicita la
   lectura, *entonces* el sistema sugiere el número de arete detectado.
2. *Dado que* el sistema no logra leer el arete, *cuando* termina el proceso, *entonces*
   informa que no se detectó el número y permite ingresarlo manualmente.

#### HU-09 — Sugerencia de raza y color/patrón

**Como** productor, **quiero** recibir sugerencias de raza y de color/patrón de pelaje a
partir de la fotografía **para** completar la ficha con menos esfuerzo.

**Prioridad:** Media · **Estimación:** 8 puntos

1. *Dado que* el animal tiene fotografía, *cuando* el productor solicita la sugerencia,
   *entonces* el sistema propone una raza y un color/patrón de pelaje como apoyo al
   llenado de la ficha.
2. *Dado que* el sistema no logra proponer una raza o un color/patrón, *cuando* termina el
   proceso, *entonces* el productor puede completar esos datos manualmente.

#### HU-10 — Corrección manual de lo sugerido por la IA

**Como** productor, **quiero** corregir manualmente los datos sugeridos por el módulo de
IA **para** asegurar que los datos de la ficha sean correctos.

**Prioridad:** Media · **Estimación:** 3 puntos

1. *Dado que* el módulo de IA sugirió el número de arete, la raza o el color/patrón,
   *cuando* el productor modifica cualquiera de esos valores, *entonces* la ficha guarda
   el valor corregido y no la sugerencia.
2. *Dado que* el módulo de IA sugirió valores, *cuando* el productor los confirma,
   *entonces* la ficha guarda los valores confirmados.

#### HU-11 — Registro guiado con mínima digitación

**Como** productor, **quiero** registrar un animal mediante pasos guiados y con mínima
digitación **para** hacerlo sin dificultad aunque tenga poca experiencia con plataformas
digitales.

**Prioridad:** Media · **Estimación:** 5 puntos

1. *Dado que* el productor inicia el registro de un animal, *cuando* avanza en el proceso,
   *entonces* el sistema lo conduce por pasos guiados.
2. *Dado que* un dato tiene opciones definidas, como la categoría de especie, *cuando* el
   productor lo completa, *entonces* lo selecciona de una lista en lugar de digitarlo.

#### HU-12 — Arete como referencia del registro oficial

**Como** productor, **quiero** que, si el animal ya está registrado oficialmente, el
número de arete se use como referencia **para** complementar su ficha sin duplicar el
registro oficial.

**Prioridad:** Media · **Estimación:** 5 puntos

1. *Dado que* el animal ya está registrado oficialmente, *cuando* el productor registra el
   animal con su número de arete, *entonces* el número de arete se guarda como referencia
   en la ficha.
2. *Dado que* el animal no está registrado oficialmente, *cuando* el productor lo registra
   con su número de arete, *entonces* el número sirve de base para iniciar la ficha.
3. *Dado que* el animal se registra en la plataforma, *cuando* se guarda la ficha,
   *entonces* el registro oficial de Trazar-Agro/SENASA no se duplica ni se modifica.

---

## Sección 07 — Planificación temporal, estimaciones y costos

### Plan temporal

### Estimaciones

### Cronograma de entregas

El proyecto se organiza en 5 Sprints de 2 semanas. La entrega oficial del Expediente
completo y la demostración del incremento se realizan en la Semana 11.

### Costos

---

## Sección 08 — Riesgos y adquisiciones

### Registro de riesgos

### Respuestas a los riesgos

### Plan de adquisiciones

---

## Sección 09 — Calidad y Definition of Done

### Criterios de calidad

Toda sugerencia generada por el módulo de IA puede corregirse manualmente.

### Definition of Done

### Estrategia de validación

La interfaz se valida con productores reales o simulados, priorizando la accesibilidad
para usuarios adultos mayores con poca experiencia en plataformas digitales.

---

## Sección 10 — Comunicación y responsabilidades del equipo

### Matriz de responsabilidades

Los roles y las responsabilidades del Scrum Team (Product Owner, Scrum Master y
Developers) se definen en la Sección 00.

### Plan de comunicación

### Working Agreements

---

## Sección 11 — Decisiones, cambios y evidencias — integración final

### Decisiones y cambios

### Evidencias

### Preparación de la demostración

---

## Sección 12 — Producto / Incremento final y cierre del proyecto

### Producto / Incremento final

### Informe final

### Demostración del incremento

### Cierre del proyecto

---

## Bibliografía y fuentes base

- Universidad Técnica Nacional. *ISW-912 Administración de Proyectos Informáticos* —
  material de Lección 1, Lección 2, Semana 2, Semana 3 y Semana 4.
- Project Management Institute. *A Guide to the Project Management Body of Knowledge
  (PMBOK® Guide), Eighth Edition.*
- Schwaber, K. & Sutherland, J. *The Scrum Guide.* November 2020.