# FRONTEND CRAFT STANDARD (v1.0)

> Material de referencia transversal de craft visual. NO es un módulo de routing:
> lo cargan M3, M5, M5.5 y M8.6 vía sus hooks (cuando el humano apruebe los diffs)
> y cualquier sesión de ejecución frontend (M8–M9.8).
> Origen: propuesta tipo M14 (2026-07-04) — "el output de Webbing sale genérico
> con olor a IA". Autoridad: Claude propone, el humano aplica (SKILL.md §7 y §13).
> Estado: ACTIVO como material de referencia. Los hooks en módulos existentes
> requieren OK del humano (ver Docs/PROPUESTA_Frontend_Craft_diffs.md).

---

## 0. PROBLEMA QUE RESUELVE

El sistema tiene disciplina de proceso (gates, fidelidad, anti-clichés por
categoría) pero el craft visual por default converge a lo promedio del modelo:
Inter centrado sobre fondo plano con tres cards. Evidencia real:

- CUORE pasó GATE 3 con el sistema de imágenes de M5 ausente; lo detectó el
  humano mirando el deploy ("es muy pobre en términos de calidad").
- Tres sitios reales compartían el mismo esqueleto (origen del Principio 10).
- M8.6 solo detecta drift contra el Mapa de Clichés de la CATEGORÍA (M5.5).
  Los tells de IA genérica (Inter como body, fondo plano, hero simétrico,
  copy hedgey) no figuran en ningún mapa → un build tibio da "AUSENTE" y pasa.

Este estándar no reemplaza a M5/M5.5/M8.6: les da el piso de craft que asumían.

**Regla madre:** lo que no sirve es lo TIBIO. Maximalismo brutal y minimalismo
refinado sirven por igual. Lo que se prohíbe es el punto medio sin decisión.

---

## 1. MANDATO — DIRECCIÓN ESTÉTICA EXTREMA Y NOMBRADA

Antes de producir cualquier frontend (mockup, hero, build), declarar por escrito:

1. **NOMBRE de la dirección** (2–5 palabras, específico, no genérico).
   - Válidos: "brutalismo atlético nocturno", "editorial de archivo suizo",
     "lujo silencioso mediterráneo", "retro-futurismo de terminal".
   - Inválidos: "moderno y limpio", "premium", "minimalista" (a secas),
     "profesional". Si el nombre le sirve a cualquier proyecto, no es un nombre.
2. **MUNDO de referencia** (1 línea): de qué universo material/cultural sale.
   Ej: "señalética de estadio + camisetas + luz de reflector sobre cemento".
3. **QUÉ EXCLUYE** (3+ ítems): decisiones que esta dirección prohíbe.
   Una dirección que no excluye nada no es una dirección.
4. **EL EXTREMO**: en qué variable esta dirección se compromete a fondo
   (escala, oscuridad, vacío, densidad, color, movimiento). "Un poco de todo"
   está prohibido.

Sin estas 4 líneas declaradas, no se produce. Es condición de entrada a
cualquier trabajo visual, y GATE 2 la hereda vía M5 (hook propuesto).

---

## 2. TIPOGRAFÍA — REGLAS DURAS

### 2.1 PROHIBIDAS COMO BODY POR DEFAULT
Inter, Roboto, Arial, Helvetica/Helvetica Neue, system-ui / -apple-system /
"system font stack", Open Sans, Lato, Poppins, Montserrat, Space Grotesk.

Excepción única: producto UI-denso (dashboard, app) donde la neutralidad es
decisión estratégica ESCRITA, con la diferenciación cargada explícitamente en
otra variable (layout, color, motion) y declarada en el Signature Brief.
"Es legible y segura" no es justificación: es la definición del default.

### 2.2 PAIRING OBLIGATORIO CON CARÁCTER
- Display y body se eligen como PAR, no por separado. El par debe producir la
  tensión útil de M3 (historia+sistema, drama+control, futuro+pasado, etc.).
- Al menos UNA de las dos familias debe tener carácter identificable: si un
  diseñador no puede nombrar qué la distingue en una línea, no tiene carácter.
- JUSTIFICACIÓN ESCRITA obligatoria: qué comunica el par (señal semiótica de
  M3), por qué ESTE proyecto y no cualquiera, y contra qué 2 alternativas
  perdió cada elección.
- Fuente única (una familia, múltiples pesos) sigue siendo válida (M3 Pairing 5)
  solo si la familia tiene carácter propio y la escala hace el trabajo de
  contraste. Fuente única con neo-grotesk neutro = default disfrazado.

### 2.3 ESCALA
- Heredar los ratios de M3, pero el hero de un proyecto con dirección extrema
  usa el extremo del sistema: clamp() con techo real (100px+ desktop cuando la
  dirección lo pide), no el hero "seguro" de 49-61px por inercia.
- Contraste de pesos visible: si todos los textos pesan 400-600, no hay sistema.

---

## 3. LOS 4 REQUISITOS DE SALIDA (hereda y endurece M5.5)

Ningún frontend sale de M5.5 (ni entra a producción vía M8–M9) sin los cuatro.
No son sugerencias: son condición de salida verificable ítem por ítem.

### R1 — ATMÓSFERA (fondo plano prohibido como default)
El fondo es una decisión, no una ausencia. Opciones válidas: gradiente con
dirección/luz, textura o grain, patrón geométrico derivado del mundo de la
marca, capas con profundidad (blur, transparencias), iluminación localizada
(glow, spotlight), o VACÍO DELIBERADO (un plano puro puede ser atmósfera si
está declarado como decisión y el resto del sistema lo sostiene — lujo
silencioso). `background: #fff` o un solo hex sin declaración = falla R1.

### R2 — MOMENTO MEMORABLE (uno, nombrable)
Un elemento que alguien describe 24 hs después sin ver el sitio ("el sitio del
número gigante que cuenta las canchas libres"). Se conecta con el Signature
System de M5/M9.8: la aparición PRIMARIA de la firma es el candidato natural.
Test: escribir la frase que diría el usuario. Si la frase sale genérica
("tenía animaciones lindas"), no hay momento.

### R3 — ASIMETRÍA / RUPTURA DE GRILLA INTENCIONAL
Al menos una decisión compositiva que rompa la simetría esperada: peso lateral,
elemento que cruza columnas o sangra del viewport, superposición texto/imagen,
diagonal, offset vertical entre columnas. El hero centrado-simétrico con dos
botones y tres cards abajo es la marca de agua de la IA: prohibido salvo
justificación escrita (ej. landing de conversión donde M5 lo pide — y aun ahí,
la asimetría puede vivir en otra sección).

### R4 — CONTRASTE BRUTAL DE ESCALA
La relación entre el elemento más grande y el texto base debe ser dramática y
buscada (guía: 8:1 o más en la pantalla de apertura cuando la dirección es
expresiva; en minimalismo refinado el contraste puede ser de vacío — un
elemento chico en un océano de espacio es el mismo requisito por la vía
opuesta). Todo del mismo tamaño ± 20% = falla R4.

---

## 4. ANTI-AI-SLOP CHECKLIST (accionable)

Correr sobre el artefacto REAL (screenshot/build, no la intención). Cada tell
presente = 1 punto. **3+ puntos = el build huele a IA → FALLA.**
1–2 puntos = corregir antes de mostrar a nadie.

| # | Tell | Cómo verificarlo |
|---|------|------------------|
| 1 | Body en Inter/Roboto/Arial/system (o de la lista 2.1) sin justificación escrita | Ver CSS computado |
| 2 | Fondo plano de un solo color sin declaración de vacío deliberado | Ver hero y secciones |
| 3 | Hero centrado simétrico: badge pill + H1 + sub + 2 botones apilados al centro | Ver composición |
| 4 | Grid de 3 cards iguales (ícono/emoji + título + párrafo) como primera sección | Ver estructura |
| 5 | Copy hedgey: "soluciones integrales", "todo en un solo lugar", "llevá X al siguiente nivel", "tu aliado en...", promesas sin sustantivo concreto ni número | Leer el copy en voz alta |
| 6 | Paleta tibia: acentos repartidos parejo, saturaciones medias, nada domina | ¿Podés decir EL color del sitio en 1 palabra? |
| 7 | Sin momento memorable (falla el test de la frase de R2) | Test 24 hs |
| 8 | Gradiente morado/azul sobre blanco u oscuro (el gradiente default del modelo) | Ver hero |
| 9 | Emojis como iconografía en un sitio de agencia | Ver cards/listas |
| 10 | Border-radius + sombra suave idénticos en TODOS los contenedores | Ver sistema de componentes |
| 11 | Escala uniforme: H1 apenas 2-3x el body | Medir |
| 12 | Ningún elemento sangra, se superpone ni rompe la grilla | Ver layout completo |

Los tells 1–12 aplican a CUALQUIER categoría, exista o no Mapa de Clichés de
M5.5 para ella. Esto cubre el agujero de M8.6 (categorías sin mapa quedaban
sin verificación de drift).

**Piso técnico innegociable (no da puntos: da bloqueo directo):**
- Contraste WCAG AA en todo texto (incluido texto sobre atmósfera/imagen).
- Responsive real: la dirección sobrevive en 375px (la firma se adapta, no se
  elimina — M9.8 Sección 4, dilución 3).
- `prefers-reduced-motion` implementado: simplifica el motion, no lo borra.
- Focus visible en todo elemento interactivo.

---

## 5. INTEGRACIÓN DE LA SKILL frontend-design EN M5–M9

La skill instalada (`frontend-design`, plugin oficial) es un ACELERADOR de
criterio de craft, subordinado al sistema. Orden de autoridad:
**concepto (M4) → percepción (M4.5) → dirección (M5) → innovación (M5.5) →
este estándar → skill frontend-design como refuerzo de ejecución.**
La skill nunca decide dirección; refuerza el compromiso al ejecutarla
(misma regla que M9.3 aplica a las librerías de componentes: el criterio
primero, el acelerador después).

Mapa de uso por módulo:

- **M5 (Visual Direction):** usar su vocabulario de tonos extremos (brutally
  minimal, maximalist, retro-futuristic, luxury/refined, editorial, brutalist,
  art deco, industrial…) como disparador para NOMBRAR la dirección (§1).
  No copiar el tono: nombrarlo para este proyecto.
- **M5.5 (Visual Innovation):** sus ejes (unexpected layouts, overlap, diagonal
  flow, grid-breaking, atmospheric backgrounds) son candidatos directos para la
  variable de innovación. Los 4 requisitos (§3) son la condición de salida.
- **M8.2/M8.4 (build):** aplicar sus reglas de implementación — CSS variables
  para el sistema de color, motion CSS-first, un solo page-load orquestado con
  reveals escalonados antes que micro-efectos dispersos.
- **M9.2/M9.3 (componentes y motion):** "high-impact moments over scattered
  micro-interactions" refuerza el Motion Budget de M9.3. No agrega patrones
  nuevos: prioriza dónde gastar el budget existente.
- **M8.6 (review):** el "NEVER" de la skill (Inter/Roboto/Arial/system, purple
  gradients, predictable layouts, cookie-cutter) está operacionalizado en el
  checklist §4. M8.6 corre el checklist, no relee la skill.
- **M12:** las direcciones que la skill sugiere NO son referencias: son tonos.
  Las referencias reales siguen entrando por M12 con anti-copy.

---

## 6. RELACIÓN CON EL RESTO DEL SISTEMA

- **No reabre módulos:** M3 sigue siendo dueño de la semiótica tipográfica;
  M5 de la dirección; M5.5 de la innovación; M9.8 de la firma. Este estándar
  fija PISOS que esos módulos asumían implícitos.
- **Proporcionalidad (SKILL.md §5):** en gobernanza Ligera el estándar NO se
  recorta — se ejecuta con medios baratos. Los 4 requisitos y el checklist son
  costo 1-2 del Innovation Cost Matrix (decisiones de diseño, no desarrollo):
  una dirección nombrada, un par tipográfico con carácter y un fondo con
  atmósfera cuestan lo mismo que sus versiones tibias.
- **CDL:** el CDL puede vetar una dirección extrema mal elegida. Este estándar
  no protege extremos incoherentes: protege contra la ausencia de compromiso.

## FAIL CONDITIONS
- Producir frontend sin dirección nombrada (§1 incompleto).
- Body en fuente de la lista 2.1 sin excepción escrita.
- Salir de M5.5 con alguno de R1–R4 ausente y sin justificación.
- Checklist §4 con 3+ tells en cualquier artefacto mostrado al humano o cliente.
- Cumplir el estándar rompiendo el piso técnico (AA, responsive, reduced-motion).

## PROMPT PARA CLAUDE
Actuá como director de craft frontend. Antes de escribir una línea de código:
declará la dirección estética con nombre, mundo, exclusiones y extremo.
Elegí el par tipográfico con carácter y justificalo contra alternativas.
Diseñá la atmósfera del fondo como decisión. Definí el momento memorable y
escribí la frase que diría el usuario 24 hs después. Rompé la simetría al menos
una vez con intención. Llevá el contraste de escala al extremo que la dirección
pide. Después ejecutá con precisión: AA, responsive, prefers-reduced-motion.
Antes de mostrar nada, corré el ANTI-AI-SLOP CHECKLIST sobre el resultado real.
Si da 3+, no lo muestres: rehacelo. Lo tibio no se entrega.
