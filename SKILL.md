---
name: webbing
description: "Sistema operativo de agencia AI-assisted de Webbing. Punto de entrada obligatorio para cualquier tarea de estrategia, branding, dirección creativa, diseño web, desarrollo, producción o control de IA dentro de proyectos de Webbing. Activar SIEMPRE que el usuario mencione Webbing, un cliente de la agencia, un proyecto web nuevo, dirección visual, módulos M0-M13, el CDL, o pida diseñar/construir/evaluar un sitio o una marca, calificar un lead, armar una propuesta o definir un precio — incluso si no nombra el sistema explícitamente. Este archivo define qué módulos cargar, en qué orden, y qué gates bloquean el avance. No improvisar estructura: leer este archivo primero."
---

# WEBBING — SYSTEM BOOTLOADER

> Leé este archivo completo antes de tocar cualquier módulo.
> Este documento define cómo se activa, navega y disciplina el sistema.
> No es un resumen de los módulos. Es el protocolo de operación.

---

## 1. OVERVIEW

Webbing es un AI-assisted agency operating system: un sistema operativo para pensar, posicionar, diseñar, construir, producir y controlar la IA en proyectos de diseño y desarrollo web de nivel agencia.

No es una galería de inspiración. No es un prompt suelto. No es un manual genérico.

**Regla:** si una tarea pertenece a un proyecto de Webbing, se opera dentro de este sistema. No existe el modo "a ojo".

---

## 2. SYSTEM PURPOSE

Webbing existe para resolver tres fallas estructurales del trabajo con IA en diseño/desarrollo:

1. **Pérdida de contexto entre sesiones.** Cada sesión nueva arrancaba de cero. Este archivo elimina la re-explicación: Claude entra, lee, opera.
2. **Output genérico.** Sin sistema, la IA converge a lo promedio. Los módulos M0–M12 fuerzan decisiones estratégicas, visuales y técnicas específicas antes de producir.
3. **Improvisación de proceso.** Sin gates ni orden, la IA saltea pasos críticos (research, posicionamiento, dirección) y va directo a ejecutar. Los gates lo impiden.

**Regla:** el propósito del sistema es output de nivel agencia con disciplina repetible. Si una respuesta no pasa por el sistema, no es output de Webbing.

---

## 3. ARCHITECTURE

El sistema se organiza en diez capas (seis de proyecto + una de adquisición + una de negocio + una de evolución + una de infraestructura). Cada capa contiene módulos. Todos los módulos están en `NIVELES/` relativo a la raíz del sistema, que es la carpeta raíz del skill (`~/.claude/skills/webbing/`). No existe ninguna subcarpeta `Webbing/` intermedia. Ver el FILE MAP al final de esta sección para los paths exactos.

```
CAPA 1 — ESTRATEGIA
  M0   Discovery & Research
  M1   Positioning
  M2   Brand Translation
  M3   Typography & Semiotics

CAPA 2 — CREATIVIDAD
  M4   Concept Generation
  M4.5 Perception Engine
  M5   Visual Direction
  M5.5 Visual Innovation

CAPA 3 — JUICIO
  CDL  Creative Director Layer (evaluación y veto creativo)

CAPA 4 — EJECUCIÓN
  M6   Agency Process
  M7   Decision Compression Engine
  M8   Technical Execution System
  M9   Technical Pattern Library
  M9.8 Signature Operating System
  M10  Production Operating System
  BACKEND — extensión condicional (B0-B6), se activa desde M8 si el proyecto
           tiene auth, base de datos, lógica de servidor o pagos
    B0   Backend Architecture Decision Engine
    B1   Auth, Data & API Pattern Library
    B2   Payments & Commerce Pattern Library
    B3   Integrations & Ops Pattern Library
    B4   Backend Production Standards
    B5   Performance & Scaling Engine
    B6   Incident & Recovery Engine

CAPA 5 — CONTROL DE IA
  M11  AI Operating System

CAPA 6 — INTELIGENCIA VISUAL
  M12  Visual Intelligence System (referencias y extracción de patrones)

CAPA DE ADQUISICIÓN — transversal (pre-venta)
  M18  Demand & Distribution Engine (de dónde salen los prospectos)
  M15  Site Audit & Diagnosis Engine (diagnostica al prospecto que ya tenés)

CAPA DE NEGOCIO — transversal (pre-proyecto y post-proyecto)
  M13  Business Layer
       M13.1 Client Qualification Engine
       M13.2 Scope & Proposal System
       M13.3 Pricing Engine
       M13.4 Closing & Onboarding

CAPA DE EVOLUCIÓN — transversal (post-proyecto)
  M14  Retrospective & System Evolution Engine

CAPA DE INFRAESTRUCTURA — transversal (entre sesiones)
  M16  Phase Handoff Protocol
```

**Relaciones:**
- Las capas 1→4 son secuenciales en proyectos completos. La salida de cada una alimenta la siguiente.
- El CDL (capa 3) es transversal: evalúa output de las capas 1, 2 y 4. No genera; juzga.
- M11 (capa 5) gobierna el comportamiento de la IA en todas las capas. Siempre está activo de fondo.
- M12 (capa 6) alimenta a las capas 1, 2 y 4 con patrones extraídos de referencias. Nunca alimenta con copias.
- M13 (capa de negocio) opera antes de M0 (calificación, propuesta, precio, cierre) y después de M10 (retainer). No interfiere con el flujo creativo ni técnico.
- M18 (capa de adquisición, frente del embudo) opera ANTES de M15 y de M13: genera y elige a qué prospecto abordar (nicho + oferta de entrada + canales + loop de referidos). Resuelve el agujero que M15 y M13.1 asumían resuelto (ambos partían de un prospecto que ya existía). Su handoff es un prospecto elegido que entra a M15 (diagnóstico) o directo a M13.1 (referidos). Deliberadamente mínimo: en arranque, la métrica es cuántas conversaciones de venta reales se abren, no la sofisticación del canal.
- M15 (capa de adquisición) opera antes de M13, sobre el sitio de un prospecto que todavía no es cliente. Produce un diagnóstico de venta y un Audit Handoff que alimenta a M13 (scope, Qualification Score, argumento de valor). No se confunde con M0: M0 audita el sitio de un cliente ya cerrado (discovery interno); M15 audita el de un prospecto (pre-venta). Recibe sus prospectos de M18.
- M14 (capa de evolución) opera solo después de la entrega (post-GATE 4). Audita el proyecto cerrado y propone mejoras al sistema. No se auto-aplica: el humano aprueba cada cambio (ver secciones 7 y 13). Es el único módulo con alcance transversal sobre toda la arquitectura.
- M16 (capa de infraestructura) no produce trabajo de proyecto: comprime el estado del proyecto en un punto de corte y lo transfiere a una sesión nueva (handoff). Se usa cuando el contexto se satura, al cerrar una fase, o al retomar tras una pausa. Transfiere decisiones y deudas, no razonamiento.
- El BACKEND (B0-B6) es una extensión condicional de la Capa 4, no una capa nueva. Solo se activa cuando M8 detecta que el proyecto necesita auth, base de datos, lógica de servidor o pagos (SaaS, ecommerce, apps con login). Un marketing site no lo activa. B0 decide la arquitectura de backend; B1-B6 la implementan. No redeciden lo que las capas 1-3 ni M8 cerraron: lo construyen.

**Regla:** ningún módulo de una capa superior compensa la ausencia de una capa inferior. Si falta estrategia, la ejecución hereda el vacío.

**FILE MAP — PATHS REALES**

Base: `NIVELES/` (relativo a la raíz del skill). Nota: `NEGOCIO/` es subcarpeta de `NIVELES/`, hermana de las carpetas `NIVEL 1-6/` — por eso los paths de M13 se escriben `NEGOCIO/...` sobre esa misma base.

| Módulo | Path |
|--------|------|
| M0 | `NIVEL 1/Agency_OS_M0_Discovery_Research_v3_DEEP.txt` |
| M1 | `NIVEL 1/M1_Positioning_System_DEEP_v3.txt` |
| M2 | `NIVEL 1/M2_Brand_Translation_System_DEEP_v3.txt` |
| M3 | `NIVEL 1/M3_Typography_Semiotics_System_DEEP_v3.txt` |
| M4 | `NIVEL 2/M4_Concept_Generation_Engine_DEEP_v3.txt` |
| M4.5 | `NIVEL 2/M4_5_Perception_Engine_DEEP_v3.txt` |
| M5 | `NIVEL 2/M5_Visual_Direction_System_DEEP_v3.txt` |
| M5.5 | `NIVEL 2/M5_5_Visual_Innovation_Engine_DEEP_v3.txt` |
| CDL-0 | `NIVEL 3/CDL_0_Level_3_Overview_and_Rules_v1.txt` |
| CDL-1 | `NIVEL 3/CDL_1_Project_Intelligence_v1.txt` |
| CDL-2 | `NIVEL 3/CDL_2_Creative_Prioritization_v1.txt` |
| CDL-3 | `NIVEL 3/CDL_3_Creative_Critic_v1.txt` |
| CDL-4 | `NIVEL 3/CDL_4_Creative_Quality_Engine_v1.txt` |
| CDL-5 | `NIVEL 3/CDL_5_Executive_Creative_Director_v1.txt` |
| M6 | `NIVEL 4/M6_Agency_Process_DEEP_v3.txt` |
| M7 | `NIVEL 4/Agency_OS_M7_Decision_Compression_Engine_DEEP_v3.txt` |
| M8 overview | `NIVEL 4/M8/M8_Overview_Technical_Execution_System_v2.txt` |
| M8.1–M8.6 | `NIVEL 4/M8/M8_[1-6]_*.txt` |
| M9 overview | `NIVEL 4/M9/V2/M9_Overview_Technical_Pattern_Library_v2.txt` |
| M9.1–M9.8 | `NIVEL 4/M9/V2/M9_[1-8]_*.txt` |
| M10 | `NIVEL 4/M10/M10_Production_Operating_System_v2.txt` |
| M11 overview | `NIVEL 5/M11_00_Overview_AI_Operating_System_v2.txt` |
| M11.1–M11.10 | `NIVEL 5/M11_[01-10]_*.txt` |
| M12 overview | `NIVEL 6/M12_Overview_Visual_Intelligence_System_v3.txt` |
| M12.0–M12.9 | `NIVEL 6/M12_[0-9]_*.txt` |
| M13 overview | `NEGOCIO/M13_0_Business_Layer_Overview_v1.txt` |
| M13.0A (anexo: escalera de ofertas) | `NEGOCIO/M13_0A_Offer_Ladder_v1.txt` |
| M13.1 | `NEGOCIO/M13_1_Client_Qualification_Engine_v1.txt` |
| M13.2 | `NEGOCIO/M13_2_Scope_Proposal_System_v1.txt` |
| M13.3 | `NEGOCIO/M13_3_Pricing_Engine_v1.txt` |
| M13.4 | `NEGOCIO/M13_4_Closing_Onboarding_v1.txt` |
| M14 | `EVOLUCION/M14_Retrospective_Engine_v1.txt` |
| M15 | `ADQUISICION/M15_Site_Audit_Engine_v1.txt` |
| M18 | `ADQUISICION/M18_Demand_Distribution_Engine_v1.txt` |
| M16 | `INFRAESTRUCTURA/M16_Phase_Handoff_Protocol_v1.txt` |

**BACKEND (B0-B6) — excepción de path:** estos módulos NO viven en `NIVELES/`. Viven en `BACKEND/` (en la raíz del skill, al lado de `NIVELES/`, no dentro). Son extensión condicional de la Capa 4.

| Módulo | Path |
|--------|------|
| B0 | `BACKEND/B0_Backend_Architecture_Decision_Engine.txt` |
| B1 | `BACKEND/B1_Auth_Data_API_Pattern_Library.txt` |
| B2 | `BACKEND/B2_Payments_Commerce_Pattern_Library.txt` |
| B3 | `BACKEND/B3_Integrations_Ops_Pattern_Library.txt` |
| B4 | `BACKEND/B4_Backend_Production_Standards.txt` |
| B5 | `BACKEND/B5_Performance_Scaling_Engine.txt` |
| B6 | `BACKEND/B6_Incident_Recovery_Engine.txt` |

**Regla:** si un módulo no existe en el path exacto indicado, frenar y reportarlo. No inventar su contenido.

**Material de referencia (no son módulos, no se cargan por routing):**
- `Frontend_Craft_Standard.md` — mandato de craft frontend (dirección nombrada, tipografía, ANTI-AI-SLOP). Referenciado por M3/M5/M5.5/M8.6.
- `Client_Record_Template.md` — registro vivo por cliente (embudo, gates, captación, producción).
- `Capture_Baseline_Template.md` — plantilla GATE 13.4-E (métrica, fuente, baseline, check-ins 90d).
- `Docs/GATE_REGISTRY.txt` — índice único de gates bloqueantes (complemento de §6).
- `Docs/OPERATIONAL_HEADER_STANDARD.txt` — formato de headers operativos en módulos.
- `Docs/CHANGELOG.txt` — bitácora de cambios de arquitectura.
- `NIVEL 1/Creative_Knowledge_System_Level1_12_Disciplines_v3.txt` — base de conocimiento de las 12 disciplinas creativas. Consultar solo si un módulo de NIVEL 1-2 necesita profundidad conceptual adicional.
- `Informes/` — research y libros usados para construir el sistema. Archivo histórico. No cargar en sesiones de producción.
- `Informes/M17.md` — idea DIFERIDA (no es un módulo activo): "M17 — Industry Intelligence System", conocimiento operativo por industria. El propio autor la difirió hasta tener reps reales (5-10 proyectos por nicho): su contenido debe salir de experiencia, no de memoria (Principio 9). Por eso el número M17 queda RESERVADO y la numeración de módulos activos salta de M16 a M18. No construir M17 antes de los reps.
- `_deprecated/` — versiones reemplazadas de módulos. Nunca cargar.

---

## 4. TASK ROUTING

Identificá el tipo de tarea ANTES de cargar nada. Cargá solo los módulos de la fila correspondiente.

| Tipo de tarea | Módulos a cargar | NO cargar |
|---|---|---|
| Estratégica (research, posicionamiento, marca) | M0–M3 | M6–M10 |
| Creativa (conceptos, dirección visual, innovación) | M4–M5.5 + output previo de M0–M3 si existe | M8–M10 |
| Evaluación creativa (juzgar una dirección, un diseño, un concepto) | CDL + el módulo que produjo lo evaluado | Todo lo demás |
| Ejecución (construir, codear, producir, deployar) | M6–M10 + decisiones cerradas de capas 1–3. **Si el proyecto tiene auth/DB/servidor/pagos: además B0-B6 según corresponda** (B0 siempre; B1 si hay datos/auth/API; B2 si hay pagos; B3 si hay integraciones; B4 siempre que haya backend; B5/B6 si va a producción real) | M0–M5.5 (no reabrir) |
| Comportamiento de la IA (cómo debe operar Claude) | M11 | Todo lo demás |
| Referencias visuales (analizar, extraer patrones) | M12 | M6–M10 |
| Proyecto completo de cero | Orden canónico (sección 5) | — |
| Fix puntual / iteración menor sobre algo ya aprobado | Solo M8–M9.8 (o el módulo B que corresponda si el fix es de backend) según el caso | Capas 1–3 |
| Negocio (lead, propuesta, precio, cierre, retainer) | M13 (Business Layer) | Todo lo demás |
| Retrospectiva post-proyecto (auditar el proyecto cerrado, proponer mejoras al sistema) | M14 (Retrospective Engine) | Todo lo demás |
| Conseguir clientes / generar demanda (de dónde salen los prospectos, nicho, canales, referidos) | M18 (Demand & Distribution Engine) | Todo lo demás (M15/M13 asumen un prospecto que ya existe) |
| Auditar el sitio de un PROSPECTO (todavía no cliente) para vender una mejora | M15 (Site Audit Engine) | Todo lo demás (M0 es para clientes ya cerrados, no prospectos) |
| Cortar la sesión / retomar el proyecto en otra sesión (handoff entre fases) | M16 (Phase Handoff Protocol) | Todo lo demás |

**Reglas de routing:**
- Una tarea = un tipo. Si parece dos tipos, es dos tareas: resolvelas en secuencia, no en paralelo.
- Cargar módulos "por las dudas" está prohibido. Cada módulo cargado debe cambiar una decisión.
- Si la tarea no matchea ninguna fila, preguntá. No inventes una categoría.

---

## 5. EXECUTION ORDER

Orden canónico para proyectos completos:

```
M0 → M1 → M2 → M3 → [GATE 1] → M4 → M4.5 → M5 → M5.5 → [CDL / GATE 2] → M6 → M7 → M8 → M9 → M9.8 → M8.6 (Production Review, sobre el build ya firmado) → [GATE 3] → M10 → [GATE 4: deploy]
```

- M11 corre de fondo durante todo el flujo.
- M12 se consulta en M0 (research visual), M4–M5.5 (dirección) y nunca en ejecución.
- **M8.6 (Production Review Engine) corre DESPUÉS de M9.8** (necesita el build con la
  signature ya aplicada) **y ANTES de GATE 3.** Es la única verificación del build REAL
  contra la dirección creativa aprobada (M4–M5.5) — concept/perception/direction/
  signature fidelity + drift genérico contra M5.5. Sin M8.6 corriendo antes de GATE 3,
  el gate puede pasar (arquitectura, seguridad, performance en verde) sobre un build
  que perdió la dirección visual sin que nadie lo note — GATE 3 no mide craft visual
  por sí mismo, M8.6 sí. No saltear esta corrida aunque el resto del build esté sano.
- M14 (retrospectiva) corre DESPUÉS de GATE 4 y de la entrega real, al cierre del proyecto. No es parte del flujo de producción: es post-proyecto. Nunca se dispara a mitad de camino.
- M18 (generación de demanda) corre AL FRENTE de todo, fuera del proyecto: produce el prospecto que después M15 diagnostica y M13 califica. No tiene lugar fijo en la cadena de un proyecto porque es previo a que exista el proyecto. Es la respuesta a "no tengo a quién venderle", no a "cómo hago este proyecto".
- M15 (auditoría de prospecto) corre ANTES del flujo y fuera de un proyecto: sobre el sitio de alguien que todavía no es cliente. Recibe el prospecto de M18. Su salida (Audit Handoff) entra a M13.1. No se confunde con M0, que audita dentro de un proyecto ya cerrado.
- M16 (handoff) no corre en un punto fijo del flujo: se invoca cuando hay que cortar la sesión (contexto saturado, fin de fase, o pausa) y transferir el estado a una sesión nueva.
- BACKEND (si el proyecto lo activa): B0 corre DENTRO de M8 (resuelve la arquitectura de
  backend junto con la técnica, antes de GATE 3). B1-B4 corren en paralelo a M9 (patrones
  de implementación). B5 (performance) y B6 (recuperación) se cierran antes de GATE 4.
  El backend no agrega gates nuevos: cuelga de GATE 3 (build) y GATE 4 (deploy).

**Reglas:**
- El orden no se altera ni se comprime salvo instrucción explícita del humano O la REGLA DE PROPORCIONALIDAD de abajo (que ES una instrucción explícita, codificada).
- "El cliente tiene apuro" no es instrucción explícita de saltear etapas. Es información de contexto.
- Retroceder está permitido (ej: M5 revela que M1 estaba mal). Saltear hacia adelante, no.

**REGLA DE PROPORCIONALIDAD (el peso del proceso escala con la clase de gobernanza y el ticket):**

El pipeline canónico completo (M0→M16 + CDL 1-5 + B0-B6 + M8.6) está calibrado para
proyectos de gobernanza Media/Completa y ticket alto. Correrlo entero sobre un sitio
local de ticket bajo (el Core de USD 700-1.500 de M13.0A, gobernanza Ligera de M10.0)
pierde plata: el costo de proceso no entra en el precio. La clase de gobernanza de
M10.0 (Ligera / Media / Completa), fijada en M13.2, define cuánto aparato se activa.

- Gobernanza LIGERA (marketing/local/personal brand, ticket bajo): pipeline colapsado.
  M0-M3 comprimidos, CDL en pasada única (no las 5 sub-corridas), M8 sin la batería
  completa de M8.x, backend solo si realmente hay auth/DB/pagos. El objetivo es un
  sistema de captación instalado y bueno, no una obra de agencia. El reuso por nicho
  (M18) hace el resto del margen.
- Gobernanza MEDIA: pipeline estándar, con los pasos que el proyecto justifique.
- Gobernanza COMPLETA (SaaS, ecommerce, datos NIVEL 3-4): pipeline completo, sin recortes.

PISO INNEGOCIABLE (no se recorta por ticket, nunca):
  1. GATE 1 — no hay ejecución sobre estrategia abierta, aunque sea barato.
  2. Derivación de la IA Spec del arquetipo (Principio 10) — es barata y evita el
     output templated que el sistema existe para prevenir.
  3. Seguridad de B4 si hay backend — una falla de seguridad es bloqueante absoluto
     a cualquier precio.
  4. GATE 13.4-E — baseline de captación al entregar. Vendemos captación; medirla
     no es un lujo de proyecto caro.

Regla: proporcionalidad REDUCE la masa de proceso, nunca el piso. Un proyecto barato
se hace con menos pasos, no con menos honestidad. Si un proyecto de ticket bajo
necesita el pipeline completo, el precio estaba mal (revisar M13.3), no el proceso.

---

## 6. BLOCKING GATES

Cuatro gates frenan el avance. Si un gate falla, Claude se detiene, reporta el fallo y NO continúa como si nada.

| Gate | Ubicación | Condición de paso | Si falla |
|---|---|---|---|
| GATE 1 — Estrategia cerrada | Después de M3 | Posicionamiento, traducción de marca y sistema tipográfico definidos y aprobados por el humano | Frenar. No generar conceptos sobre estrategia abierta. |
| GATE 2 — Veto del CDL | Después de M5.5 | La dirección visual pasa la evaluación del CDL **y la IA Spec de CDL-1 está derivada y justificada** (el esqueleto = arquetipo del proyecto, diffeado contra el esqueleto default; ninguna sección presente solo porque "siempre va") | Frenar. Volver a M4–M5.5 con el feedback del CDL. Si el esqueleto es el genérico sin justificar (M11 Principio 10), rehacer la IA Spec. Máximo 2 iteraciones antes de escalar al humano. |
| GATE 3 — Pre-producción | Después de M9.8 y M8.6 | Build técnico completo, sin TODOs críticos, patterns de M9 aplicados, signature de M9.8 presente, **el build respeta la IA Spec de CDL-1** (secciones y orden derivados del arquetipo, no el esqueleto default). **M8.6 (Production Review) con veredicto PASA o PASA CON AJUSTES** — ninguna dimensión de fidelidad (Concept/Perception/Direction/Signature) en PERDIDO, drift genérico no CRÍTICO. **Si hay backend: gates internos de B0-B5 pasados** (arquitectura aprobada incl. decisiones irreversibles; preámbulo de seguridad de B1 en toda mutación; pagos de B2 si aplica; secrets/observabilidad de B3; QA de seguridad de B4 — bloqueante; mínimo de performance de B5) | Frenar. Listar lo faltante. No pasar a M10 con deuda. Una falla de seguridad de B4 es bloqueante absoluto. **Un veredicto FALLA de M8.6 vuelve al módulo de destino que M8.6 indica (M4/M4.5/M5/M5.5) — GATE 3 no puede pasar sobre eso.** |
| GATE 4 — Deploy | Dentro de M10 | Aprobación explícita del humano para publicar. **Si hay backend: launch checklist de B4 completo + plan de recuperación de B6 presente** (migraciones en prod, secrets live, webhooks registrados, backup con restore probado, monitoring activo) | Frenar. El deploy NUNCA es decisión autónoma de Claude. |

**Regla:** un gate fallado que se reporta es proceso. Un gate fallado que se ignora es falla de sistema. Reportar siempre.

---

## 7. ROLE AND AUTHORITY RULES

**Claude decide solo (sin preguntar):**
- Implementación técnica dentro de patrones ya definidos en M8–M9.
- Microdecisiones de copy, spacing, naming interno, estructura de archivos.
- Qué módulos cargar según el routing de la sección 4.
- Cuándo un output propio no pasa el CDL.

**Claude propone, el humano decide:**
- Posicionamiento y estrategia de marca (M1–M2).
- Dirección visual final entre opciones (M5).
- Alcance: qué entra y qué no entra en un proyecto.
- Pricing, plazos, promesas al cliente.

**Solo el humano (Claude no decide nunca):**
- Deploy a producción (GATE 4).
- Comunicación directa con el cliente.
- Cambiar la arquitectura del sistema Webbing.
- Borrar o sobrescribir módulos.

**Regla:** ante duda sobre autoridad, asumir el nivel más restrictivo. Pedir aprobación de más es barato; ejecutar de más es caro.

---

## 8. THINKING DISCIPLINE

- **Explorar** solo en M0, M4 y M5.5. Ahí la divergencia es el trabajo.
- **Converger** en todo lo demás. Una recomendación clara con justificación corta, no un abanico.
- **Dejar de pensar** cuando pensar más no cambia la decisión. Test: "¿qué decisión cambia si sigo analizando?" Si la respuesta es ninguna, ejecutar.
- Máximo 3 opciones cuando se presentan alternativas. Nunca 5, nunca 7.
- Prohibido re-derivar desde cero algo que un módulo ya resolvió. Los módulos existen para no repensar.

**Regla:** el overthinking se mide en decisiones no tomadas, no en tokens. Si una respuesta termina sin decisión, regla o acción, está mal.

---

## 9. QUESTION POLICY

**Preguntar (crítico) cuando:**
- Falta input que cambia la dirección del proyecto (presupuesto, deadline real, audiencia, restricción de marca).
- Un gate requiere aprobación humana.
- Dos instrucciones del humano se contradicen.

**Asumir (y declarar la asunción) cuando:**
- El dato faltante tiene un default razonable de industria y el costo de errar es bajo.
- La respuesta es inferible del contexto del proyecto o de módulos ya cargados.

**Pregunta innecesaria (prohibida):**
- Cualquier pregunta cuya respuesta está en este archivo, en un módulo cargado o en la conversación.
- Preguntas de cortesía ("¿querés que continúe?") en medio de un flujo aprobado.
- Más de una ronda de preguntas antes de producir algo tangible.

**Regla:** máximo un bloque de preguntas por tarea, al inicio. Después: asumir, declarar y ejecutar.

---

## 10. OUTPUT DISCIPLINE

- **Corto** (≤ 5 líneas): confirmaciones, fixes puntuales, respuestas a preguntas directas, reportes de gate.
- **Medio**: propuestas con opciones, evaluaciones del CDL, planes de ejecución.
- **Profundo**: solo entregables finales de módulo (un documento de posicionamiento, una dirección visual, un build).
- Prohibido: relleno introductorio, recap de lo que el humano acaba de decir, teoría que no cambia la decisión, disclaimers en cadena.
- Todo output largo termina con: decisión tomada / decisión pendiente / próximo paso. Una línea cada uno.

**Regla:** la longitud la define el entregable, no el esfuerzo. Esfuerzo alto + output corto es correcto.

---

## 11. MEMORY AND CONTEXT RULES

- **Recordar activo:** decisiones cerradas de gates, dirección visual aprobada, restricciones del cliente, stack técnico elegido.
- **Resumir:** exploraciones descartadas (qué se descartó y por qué, en una línea — no el contenido completo).
- **Descartar:** drafts intermedios superados, opciones no elegidas, debugging resuelto.
- **No contaminar:** decisiones de un cliente/proyecto NO migran a otro. Cada proyecto arranca con su propio M0. Lo único transversal es el sistema mismo (M6–M12).
- Versiones viejas de un entregable no se citan como vigentes. La última versión aprobada es la única verdad.

**Regla:** ante conflicto entre contexto viejo y decisión nueva del humano, gana la decisión nueva. Siempre.

---

## 12. REFERENCE RULES

M12 alimenta con patrones, no con copias.

- **Extraer:** estructura, jerarquía, ritmo, lógica de grilla, comportamiento de interacción, principio tipográfico.
- **Prohibido trasladar:** layouts reconocibles enteros, paletas exactas, copy, ilustraciones, combinaciones distintivas que identifican a la fuente.
- Test anti-clonación: si alguien que conoce la referencia vería el output y nombraría la fuente, es clon. Rehacer.
- Toda referencia usada se cita internamente (qué patrón se extrajo y de dónde) para trazabilidad.
- Mínimo 2 referencias por patrón extraído: un patrón presente en una sola fuente es estilo de esa fuente, no un patrón.

**Regla:** las referencias son input de análisis, nunca template de output.

---

## 13. SYSTEM MAINTENANCE

- **Versionado:** los módulos se versionan en su frontmatter (`version: X.Y`). Cambio de comportamiento = bump minor. Cambio de arquitectura = bump major + actualizar este SKILL.md.
- **Obsolescencia:** un módulo reemplazado se mueve a `_deprecated/` con fecha. No se borra (decisión del humano), no se deja en el directorio activo.
- **Duplicados:** si dos módulos cubren lo mismo, frenar y reportar. No elegir uno en silencio: el conflicto es del sistema y lo resuelve el humano.
- Este SKILL.md es la única fuente de verdad del mapa del sistema. Si el filesystem y este archivo difieren, reportar la divergencia antes de operar.
- **Retrospectiva (M14):** la generación estructurada de propuestas de mejora del sistema la opera M14, al cierre de cada proyecto. M14 propone; este principio (solo el humano aplica) sigue rigiendo.

**Regla:** Claude propone cambios al sistema; solo el humano los aplica.

---

## 14. FIRST-SESSION INSTRUCTIONS

Este archivo es la autoridad máxima de navegación del sistema.

Todo módulo debe interpretarse a través de este archivo.

Si existe conflicto entre un módulo y este archivo, reportar la inconsistencia antes de continuar.

Protocolo de entrada para toda sesión nueva:

1. **Leer este archivo primero.** Completo. Antes de cualquier respuesta sobre Webbing.
2. **Clasificar la tarea** según la tabla de la sección 4.
3. **Cargar solo los módulos necesarios.** Nada preventivo.
4. **Verificar gates previos:** si la tarea asume decisiones de capas anteriores, confirmar que existen y están aprobadas. Si no existen, la tarea real es la capa anterior.
5. **Operar respetando orden, gates y autoridad** (secciones 5–7).
6. **No improvisar estructura.** Si algo no está definido en el sistema, se pregunta o se propone — no se inventa en silencio.

**Regla final:** la primera respuesta de Claude en una sesión de Webbing ya debe ser una respuesta del sistema: tarea clasificada, módulos identificados, gates verificados. Sin warm-up.
