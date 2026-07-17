# WEBBING — M12 REFERENCE LIBRARY

> Fuente de verdad persistente para el sistema de M12 (Visual Intelligence
> System). Sin este archivo, los criterios cuantificados de M12 — apariciones
> de un patrón (M12.4), promoción a "standard" por uso en 5+ proyectos
> (M12.9), degradación por Deprecation Threshold, gaps de búsqueda
> (M12.8/M12.9) — no tienen dónde persistir entre sesiones. Es la misma clase
> de hueco que motivó `Docs/PORTFOLIO_REGISTRY.md` y `Docs/M14_PROPOSAL_LOG.txt`,
> aplicada acá a M12. Ver `Docs/CHANGELOG.txt`, entrada 2026-07-16.

**Quién escribe acá:**
- M12.1 agrega la fila de la referencia al pasar el Collection Gate (GATE 12-A).
- M12.2 completa las columnas del formato estándar de clasificación.
- M12.4 registra cada patrón extraído (Pattern Formula) y actualiza su
  contador de apariciones — el dato que M12.4 necesita para declarar
  emergent/validated y que M12.9 necesita para promover a standard.
- M12.6 escribe el score (promedio /11 dimensiones) en la fila de la referencia.
- M12.8 lee este archivo ANTES de declarar "sin resultados", y agrega una fila
  a GAPS DE BÚSQUEDA cuando no encuentra coincidencias.
- M12.9 actualiza el estado del ciclo de vida (emergent/validated/standard/
  legacy/deprecated) de referencias y patrones, y revisa los gaps registrados.

**Regla de honestidad** (mismo criterio que PORTFOLIO_REGISTRY.md): un campo
sin dato se marca `—`, nunca se inventa. Un score o un contador de apariciones
sin fuente real es peor que un campo vacío.

**Regla de trazabilidad:** ninguna fila nueva se agrega sin haber pasado
realmente por el Collection Gate (M12.1) y sin que la clasificación (M12.2)
salga del formato estándar real, no de memoria de sesión.

--------------------------------------------------------------------------------

## REGISTRO DE REFERENCIAS

Una fila por referencia que pasó GATE 12-A. Columnas = formato estándar de M12.2 + score de M12.6.

| Nombre/URL | Industria dominante | Industrias secundarias | Tipo UX | Tipo layout | Tipo motion | Tipo tipografía | Innovación | Riesgo | Firma visual | Reutilización | Estado | Etiquetas de recuperación | Score (M12.6, /10) | Patrones asociados |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| — | — | — | — | — | — | — | — | — | — | — | — | — | — | — |

*(vacío — se puebla con la primera referencia real que pase el Collection Gate de una corrida de M12)*

--------------------------------------------------------------------------------

## LOG DE PATRONES

Un patrón por fila. El contador de apariciones es el dato que M12.4 necesita
para pasar de emergent a validated (2+ referencias) y que M12.9 necesita para
el Promotion Criteria (5+ proyectos → standard) y el Deprecation Threshold.

| Patrón | Pattern Formula | Referencias donde aparece | Apariciones | Estado | Última revisión |
|---|---|---|---|---|---|
| — | — | — | 0 | emergent | — |

*(vacío — se puebla cuando M12.4 extrae el primer patrón con Pattern Formula completa que pasa el Validation Test)*

--------------------------------------------------------------------------------

## GAPS DE BÚSQUEDA

Registrado por M12.8 cuando una búsqueda de retrieval no encuentra resultados
(protocolo "sin resultados" de M12.8). Alimenta M12.1 (qué adquirir) y la
Evolution Review de M12.9.

| Fecha | Intención buscada | Criterios usados | Gap detectado | Prioridad adquisición |
|---|---|---|---|---|
| — | — | — | — | — |

--------------------------------------------------------------------------------

## Mantenimiento

Actualizar la fila de una referencia al pasar cada gate de M12 (no esperar a
tener el ciclo M12.1→M12.9 completo — una fila puede estar parcial mientras
la referencia sigue en evaluación, igual que PORTFOLIO_REGISTRY.md). Actualizar
el contador de un patrón cada vez que aparece en una nueva referencia — es el
evento que dispara la revisión de Promotion Criteria en M12.9. Registrar
cambios de arquitectura en `Docs/CHANGELOG.txt`.

Este archivo nace vacío (2026-07-16): M12 no corrió de punta a punta en ningún
proyecto de práctica todavía, así que no hay datos reales que migrar desde
memoria de sesión — hacerlo sería repetir exactamente el bug de fila fantasma
que `PORTFOLIO_REGISTRY.md` ya tuvo que corregir dos veces (INC-1 Cursor Café,
INC-1 Estudio de Tatuaje).

Hallazgo original: auditoría M12→M18, `Docs/CHANGELOG.txt` 2026-07-16.
