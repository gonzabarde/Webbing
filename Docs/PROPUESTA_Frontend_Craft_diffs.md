# PROPUESTA — HOOKS DEL FRONTEND CRAFT STANDARD EN M3 / M5 / M5.5 / M8.6

Estado: **APLICADO 2026-07-04** (hooks integrados en M3 v3.1, M5 v3.1, M5.5 v3.1, M8.6 v2.1).
Fecha propuesta: 2026-07-04. Origen: propuesta tipo M14 sobre craft de frontend.
Referencia: `Frontend_Craft_Standard.md` (raíz del skill — ya creado, aditivo).

Regla de aplicación: cada diff es una INSERCIÓN (más el bump de versión en el
título). Nada existente se borra ni se reescribe, salvo las líneas marcadas
con `-` en el diff de M8.6 (sección DEFINICIÓN DE GENÉRICO y veredicto), que
se reemplazan por versiones más estrictas manteniendo todo lo que ya cubrían.
Para revertir: quitar los bloques insertados y restaurar el número de versión.

---

## DIFF 1 — M3 (`NIVEL 1/M3_Typography_Semiotics_System_DEEP_v3.txt`) v3 → v3.1

```diff
-MÓDULO 3 — TYPOGRAPHY & SEMIOTICS SYSTEM (v3 DEEP)
+MÓDULO 3 — TYPOGRAPHY & SEMIOTICS SYSTEM (v3.1 DEEP)
```

Insertar después de la sección "LÓGICA DE PAIRING — POR TENSIÓN ÚTIL [v3]"
(después de la línea "- Cuando la categoría es tan conservadora que dos fuentes parecen exceso."):

```diff
+REGLA DE PAIRING DISTINTIVO + FUENTES PROHIBIDAS POR DEFAULT [v3.1]
+--------------------------------------------------------------------
+(Hook del Frontend_Craft_Standard.md §2 — el estándar es la fuente de verdad.)
+
+PROHIBIDAS COMO BODY POR DEFAULT:
+Inter, Roboto, Arial, Helvetica/Helvetica Neue, system-ui / -apple-system,
+Open Sans, Lato, Poppins, Montserrat, Space Grotesk.
+Excepción única: producto UI-denso donde la neutralidad es decisión
+estratégica ESCRITA y la diferenciación está cargada en otra variable
+declarada en el Signature Brief. "Es legible y segura" no es justificación.
+
+PAIRING DISTINTIVO OBLIGATORIO:
+- Display y body se eligen como PAR que produce una tensión útil (arriba).
+- Al menos una familia con carácter identificable: si no se puede nombrar
+  en una línea qué la distingue, no tiene carácter.
+- Justificación escrita: señal semiótica del par + por qué ESTE proyecto
+  + contra qué 2 alternativas perdió cada elección.
+- Fuente única sigue válida (Pairing 5) solo si la familia tiene carácter
+  propio. Fuente única con neo-grotesk neutro = default disfrazado.
```

Insertar en FAIL CONDITIONS (al final de la lista existente):

```diff
+- El body usa una fuente de la lista de prohibidas por default sin la
+  excepción escrita (Frontend_Craft_Standard.md §2.1).
+- El pairing no tiene justificación contra alternativas.
```

---

## DIFF 2 — M5 (`NIVEL 2/M5_Visual_Direction_System_DEEP_v3.txt`) v3 → v3.1

```diff
-MÓDULO 5 — VISUAL DIRECTION SYSTEM (v3 DEEP)
+MÓDULO 5 — VISUAL DIRECTION SYSTEM (v3.1 DEEP)
```

Insertar en PROCESO CLAUDE, como paso 0 antes del paso 1
("1. Definir una sola firma visual principal."):

```diff
+0. Declarar la DIRECCIÓN ESTÉTICA NOMBRADA antes de producir nada.
+   (Hook del Frontend_Craft_Standard.md §1.) Cuatro líneas obligatorias:
+   NOMBRE (2-5 palabras, específico — "moderno y limpio" no es un nombre),
+   MUNDO de referencia (1 línea), QUÉ EXCLUYE (3+ ítems),
+   EL EXTREMO (en qué variable se compromete a fondo).
+   Sin las 4 líneas, este módulo no avanza. GATE 2 las hereda como
+   parte de la dirección visual que el CDL evalúa.
```

Insertar en OUTPUT (como ítem 0 o al inicio):

```diff
+0. Dirección estética nombrada (nombre + mundo + exclusiones + extremo).
```

Insertar en FAIL CONDITIONS:

```diff
+- No hay dirección estética nombrada, o el nombre le serviría a cualquier
+  proyecto de cualquier categoría.
```

---

## DIFF 3 — M5.5 (`NIVEL 2/M5_5_Visual_Innovation_Engine_DEEP_v3.txt`) v3 → v3.1

```diff
-MÓDULO 5.5 — VISUAL INNOVATION ENGINE (v3 DEEP)
+MÓDULO 5.5 — VISUAL INNOVATION ENGINE (v3.1 DEEP)
```

Insertar después del PROCESO CLAUDE (después del paso 7,
"Definir cómo sostener la coherencia."):

```diff
+CONDICIÓN DE SALIDA — 4 REQUISITOS DE CRAFT [v3.1]
+----------------------------------------------------
+(Hook del Frontend_Craft_Standard.md §3.) Ninguna dirección sale de este
+módulo hacia GATE 2 sin verificar los cuatro, ítem por ítem:
+
+R1 ATMÓSFERA: el fondo es una decisión (gradiente con luz, textura/grain,
+   patrón, capas, iluminación — o vacío DELIBERADO declarado). Fondo plano
+   sin declaración = falla.
+R2 MOMENTO MEMORABLE: uno, nombrable. Test: escribir la frase que diría el
+   usuario 24 hs después. Frase genérica = no hay momento.
+R3 ASIMETRÍA / RUPTURA DE GRILLA: al menos una decisión compositiva que
+   rompa la simetría esperada. Hero centrado-simétrico default = falla
+   salvo justificación escrita de M5.
+R4 CONTRASTE BRUTAL DE ESCALA: relación dramática y buscada entre el
+   elemento mayor y el texto base (o su inverso por vacío en minimalismo
+   refinado). Todo del mismo tamaño ±20% = falla.
+
+Los 4 son costo 1-2 del Innovation Cost Matrix: no se recortan por
+proporcionalidad (gobernanza Ligera los ejecuta con medios baratos).
```

Insertar en FAIL CONDITIONS:

```diff
+- La dirección sale del módulo con alguno de R1-R4 ausente y sin
+  justificación escrita (Frontend_Craft_Standard.md §3).
```

---

## DIFF 4 — M8.6 (`NIVEL 4/M8/M8_6_Production_Review_Engine_v2.txt`) v2 → v2.1

Este es el único diff con reemplazo (no solo inserción): "Generic Drift" pasa
de comparación blanda contra el mapa de categoría a CHECKLIST DURO que puede
dar FALLA por sí solo y bloquea GATE 3.

```diff
-M8.6 — PRODUCTION REVIEW ENGINE (v2)
+M8.6 — PRODUCTION REVIEW ENGINE (v2.1)
```

En INPUTS OBLIGATORIOS, agregar:

```diff
+- Frontend Craft Standard (Frontend_Craft_Standard.md — checklist §4)
```

En PROCESO CLAUDE, reemplazar el paso 3:

```diff
-3. Verificar drift genérico.
-   Comparar el build contra el Mapa de Clichés de M5.5
-   correspondiente a la categoría del proyecto.
-   ¿La implementación se parece a alguno de los clichés listados?
+3. Verificar drift genérico — CHECKLIST DURO (dos capas, ambas obligatorias):
+   a) Clichés de CATEGORÍA: comparar contra el Mapa de Clichés de M5.5
+      (como hasta ahora). Si la categoría no tiene mapa, esta capa se omite
+      declarándolo — la capa b) NUNCA se omite.
+   b) Tells de IA: correr el ANTI-AI-SLOP CHECKLIST completo
+      (Frontend_Craft_Standard.md §4, tells 1-12) sobre el build REAL
+      (screenshot/staging, no la intención). Registrar el puntaje.
```

Reemplazar la sección DEFINICIÓN DE GENÉRICO (conserva todo lo existente y
agrega la capa de tells):

```diff
 Si el build replica 2 o más clichés de la categoría: drift genérico CRÍTICO.
 Si replica 1: drift genérico LEVE.
 Si no replica ninguno: AUSENTE.
+
+CAPA 2 — TELLS DE IA (Frontend_Craft_Standard.md §4) [v2.1]:
+Si el build acumula 3+ tells del checklist: drift genérico CRÍTICO,
+  aunque no replique ningún cliché de categoría. El build huele a IA.
+Si acumula 1-2 tells: drift genérico LEVE como mínimo (no puede ser AUSENTE).
+Si acumula 0: la capa 2 no modifica el resultado de la capa 1.
+El resultado final de Generic Drift es el PEOR de las dos capas.
+Además, verificar el piso técnico del estándar (AA, responsive 375px,
+prefers-reduced-motion, focus visible): cualquier ausencia es problema
+CRÍTICO de QA — bloquea el veredicto PASA por la vía del QA report.
```

En VEREDICTO FINAL, dentro de FALLA, la línea "Drift genérico CRÍTICO." ya
cubre el caso nuevo (la capa 2 puede producirlo). Agregar la aclaración:

```diff
 FALLA
   Cualquier campo en PERDIDO.
   Problemas críticos del QA sin resolver.
   Falla cross-browser.
   Drift genérico CRÍTICO.
+  (El drift CRÍTICO puede venir de la capa de categoría O de la capa de
+  tells de IA: 3+ tells del ANTI-AI-SLOP CHECKLIST = FALLA, sin excepción.
+  GATE 3 no puede pasar sobre este veredicto — SKILL.md §6.)
```

En DESTINOS EN CASO DE FALLA, extender el destino de Generic Drift:

```diff
 Generic Drift CRÍTICO → volver a M5.5 Visual Innovation Engine.
   El build se convirtió en una plantilla de la categoría.
   Necesita una desviación real en al menos una variable.
+  Si el CRÍTICO vino de la capa de tells de IA con la dirección de M5/M5.5
+  intacta en papel: el problema es de ejecución, no de dirección — corregir
+  en el build contra el checklist §4 y re-correr M8.6 (no reabrir M5.5).
+  Si la dirección misma era tibia (sin nombre, sin extremo): volver a M5
+  paso 0 (dirección nombrada) y de ahí a M5.5.
```

En FAIL CONDITIONS del módulo, agregar:

```diff
+- El veredicto se emitió sin correr el ANTI-AI-SLOP CHECKLIST sobre el
+  build real, o sin registrar el puntaje de tells.
```

---

## NOTA SOBRE SKILL.md (sin diff)

GATE 3 ya exige "M8.6 con veredicto PASA o PASA CON AJUSTES" y "drift genérico
no CRÍTICO" (SKILL.md §6). Como el diff 4 hace que 3+ tells = drift CRÍTICO =
FALLA, el bloqueo de GATE 3 queda cableado SIN tocar SKILL.md. No se propone
cambio de arquitectura (no hay bump major).

## ORDEN DE APLICACIÓN SUGERIDO
1. Diff 4 (M8.6) — es el que cierra el agujero de detección.
2. Diff 2 (M5) y Diff 3 (M5.5) — condiciones de entrada/salida creativas.
3. Diff 1 (M3) — reglas tipográficas.
Cada diff es independiente: se puede aprobar/rechazar por separado.
