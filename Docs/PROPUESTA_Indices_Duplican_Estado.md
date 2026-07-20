# PROPUESTA — ÍNDICES QUE DUPLICAN ESTADO

> Auditoría transversal pedida por el humano el 2026-07-19, tras tres incidentes
> del mismo día.
>
> ## ✅ ESTADO: LAS 4 REGLAS APLICADAS (2026-07-19)
>
> El humano aprobó y se aplicaron las cuatro. Este documento queda como el
> **razonamiento y la evidencia** detrás de ellas; la regla vigente vive en
> `SKILL.md §13` (FUENTE), no acá.
>
> - **R2** (apuntar, no resumir estado) → SKILL.md §13 · CHANGELOG 2026-07-19 (5)
> - **R3** (notas con condición de borrado) → SKILL.md §13 · idem
> - **R1** (declaración de fuente por bloque) → SKILL.md §13 + los 4 índices ·
>   CHANGELOG 2026-07-19 (10)
> - **R4** (integridad de cita generalizada) → SKILL.md §13 · idem
>
> Hallazgo adicional que apareció al aplicar R1: `GATE_REGISTRY` declaraba
> **co-autoridad** ("fuente operativa junto con SKILL.md §6"). Dos archivos
> reclamando autoridad sobre el mismo hecho es el estado en el que ninguno es la
> fuente — y fue lo que permitió que la cláusula de fase arranque quedara con
> alcance viejo ahí mientras M13.4 ya decía otra cosa. Retirado: un hecho, una
> fuente. La prohibición de co-autoridad quedó escrita en SKILL.md §13.

---

## 1. EL PATRÓN

Webbing tiene varios archivos que **reafirman estado que ya vive en otro lado**.
Cuando la fuente cambia y el índice no, el índice no queda vacío: queda **afirmando
algo falso con la misma autoridad de antes**. Y como es más corto y más cómodo de
leer, se consulta primero — así que la mentira gana.

Cuatro ocurrencias verificadas **en un solo día**:

| # | Índice | Qué afirmaba | Realidad | Consecuencia real |
|---|---|---|---|---|
| 1 | `M14_PROPOSAL_LOG` — resumen PENDIENTES | "quedan 8 pendientes (P1,P4,P5,P6,P8,P9,P10,P11)" | Las filas ya marcaban P1/P8/P9 Aplicada; verificando contra archivos, pendientes reales = 3 | Reporté 8 al humano. Estuve por re-aplicar 2 fixes ya hechos |
| 2 | Cláusula de arranque, 4 ubicaciones | Solo relevaba GATE 13.4-A | Debía relevar también 13.3-B | Un cierre de intercambio correcto fallaba un gate por construcción |
| 3 | `SYSTEM FILE MAP` — NOTA DE PATHS | "SKILL.md omite el prefijo `NIVELES/`" | SKILL.md **lo incluye** desde que se aplicó VINCA-P5 | La nota escrita para explicar la divergencia **pasó a ser** la divergencia |
| 4 | `M14_PROPOSAL_LOG` — REF Estudio Contable | "confirma el patrón de Runa-P5" | Es **VINCA-P5**; Runa-P5 es otra cosa | Índice citando el ID equivocado |

**Tres filas del log estaban stale** (Runa-P5, Runa-P6, VINCA-P5): propuestas ya
aplicadas que seguían figurando "Pendiente de aprobación".

---

## 2. NO TODOS LOS ÍNDICES SON IGUALES

La distinción que el sistema no hace hoy, y que ordena todo lo demás:

**(a) ÍNDICE PUNTERO — dice DÓNDE está algo, no QUÉ dice.**
Ej: `SKILL.md §3 FILE MAP`, el árbol de `SYSTEM FILE MAP`.
Riesgo **bajo**: si diverge, el path no resuelve y se detecta en el intento. Falla
ruidosa. No necesita regla nueva.

**(b) ÍNDICE RESUMEN — reafirma estado mutable que vive en otro lado.**
Ej: el resumen PENDIENTES del `M14_PROPOSAL_LOG`, la NOTA DE PATHS, las
descripciones de la cláusula de arranque en `GATE_REGISTRY`/`M13.0`/`M13.3`.
Riesgo **alto**: diverge en **silencio** y se lee como fuente. **Este es el único
tipo que falla, y los 4 casos de arriba son todos de este tipo.**

**(c) REGISTRO PRIMARIO — el estado vive acá y en ningún otro lado.**
Ej: `CHANGELOG` (histórico append-only), `PORTFOLIO_REGISTRY` (fuente de Principio 10).
**No es duplicación.** No aplica nada de esto.

El problema no es "tenemos índices". Es que **(b) no está distinguido de (c)**, y
se le da a un resumen la autoridad de un registro primario.

---

## 3. REGLAS PROPUESTAS

### Regla 1 — Declaración de fuente, obligatoria por bloque
Todo índice declara, por bloque, `FUENTE: <archivo/sección>` o
`FUENTE ÚNICA: este archivo`. Sin esa línea no se sabe si lo que se lee es la
verdad o el eco de la verdad.
*Precedente que ya funciona:* hoy se agregó `FUENTE ÚNICA: M13.4` a las entradas
de la cláusula en `GATE_REGISTRY`, y la reconciliación quedó inequívoca.

### Regla 2 — Un índice puede APUNTAR a estado mutable, nunca RESUMIRLO
Un resumen no puede reafirmar un estado que ya vive en una fila o módulo
(`Pendiente/Aplicada`, `≥50 vs ≥60`, "quedan N").
- ❌ "Quedan P1, P4, P5, P6, P8, P9, P10, P11 pendientes"
- ✅ "Estado por propuesta: ver la columna Disposición de las filas de arriba"

Un conteo (`N pendientes`) es estado derivado: se recalcula al leer, no se escribe.
**Esta sola regla habría evitado los casos 1 y 4.**

### Regla 3 — Toda nota de divergencia declara su condición de borrado
Una nota que existe para explicar una discrepancia es **temporal por naturaleza**.
Debe nombrar qué la hace desaparecer: *"borrar esta nota cuando X se aplique."*
**Esta regla habría evitado el caso 3**, que es el más instructivo del set: la nota
sobrevivió a lo que explicaba y se convirtió en el error.
Es el mismo mecanismo del `sunset` que la cláusula de arranque ya usa bien — se
propone generalizarlo de las excepciones a las notas explicativas.

### Regla 4 — Verificar contra la fuente antes de actuar sobre lo que dice un índice
Generalizar a **todos** los índices la REGLA DE INTEGRIDAD DE CITA que hoy solo
tiene `PORTFOLIO_REGISTRY`.
*Evidencia de que funciona:* esa regla nació de la fila fantasma de Cursor Café
(INC-1) y en la corrida ESTUDIO DE TATUAJE **Claude agarró solo** una tercera fila
fantasma antes de confiar en ella. El mecanismo está probado; falta extenderlo.
*Evidencia de que falta extenderlo:* hoy reporté 8 pendientes leyendo un resumen
sin verificar las filas — exactamente lo que esta regla prohíbe, en un índice que
no la tiene.

---

## 4. YA APLICADO (correcciones de hechos falsos, no arquitectura)

Estas tres no son cambio de arquitectura sino corrección de afirmaciones falsas
verificadas contra los archivos; se aplicaron el 2026-07-19:

1. `SYSTEM FILE MAP` — NOTA DE PATHS corregida (afirmaba lo opuesto a SKILL.md §3),
   con la historia de por qué estaba al revés.
2. `M14_PROPOSAL_LOG` — VINCA-P5 marcada Ya aplicada, verificada contra SKILL.md §3.
3. `M14_PROPOSAL_LOG` — REF de Estudio Contable: cita corregida de Runa-P5 a VINCA-P5.

Más las de la sesión previa: resumen PENDIENTES de runa reescrito (cero pendientes),
Runa-P5/P6 marcadas ya aplicadas, y la cláusula de arranque sincronizada en sus 4
ubicaciones.

---

## 5. LO QUE **NO** PROPONGO

- **Eliminar los índices.** `GATE_REGISTRY` y `SYSTEM FILE MAP` tienen valor real:
  se consultan rápido y evitan cargar módulos enteros. El problema es la autoridad
  ambigua, no la existencia.
- **Automatizar la verificación.** Sería lo correcto en un repo con CI; acá no hay
  dónde correrlo y construirlo antes de que duela viola la regla de reps del North
  Star (M13.0A). Las 4 reglas son de escritura y se pagan solas.
- **Tocar el CHANGELOG histórico.** Las entradas viejas describen el estado de su
  momento. Reescribirlas borraría la evidencia de por qué existen los fixes.

---

## 6. SEVERIDAD

**Media.** Ninguna ocurrencia causó daño irreversible ni tocó seguridad. Pero:
- la frecuencia es alta (4 en un día, sin buscarlas — aparecieron solas al operar);
- el modo de falla es **silencioso**, que es la característica que el sistema trata
  como agravante en todos lados (verde falso de M8.6, fila fantasma, "0 revisados");
- y el costo concreto ya se materializó dos veces hoy: un gate que fallaba por
  construcción, y trabajo casi duplicado sobre fixes ya aplicados.

**Recomendación:** aplicar las reglas 2 y 3 primero — son las que atajan los 3 de
los 4 casos, y son puramente de escritura (costo ~0). Las reglas 1 y 4 son más
invasivas porque tocan el formato de varios archivos; pueden ir después.
