# REACT BITS — CATÁLOGO COMPLETO (material de referencia de Webbing)

> Fuente: repo oficial `DavidHDev/react-bits` (relevado 2026-07-08, research vivo).
> Complementa `Frontend_Craft_Standard.md` §5.1 (parámetros de uso). Este archivo es el
> inventario + la lente del sistema (qué recurso sirve para qué requisito de craft, qué
> homogeneiza, qué cuida). NO es routing: se consulta al ejecutar un momento-firma.
> Total: **135 componentes** en 4 categorías (23 texto · 45 backgrounds · 37 components · 30 animations).

## Cómo leer este catálogo (mapa a los requisitos §3 del estándar)
- **→ R2 (momento memorable):** text animations = el reveal del headline-firma.
- **→ R1 (atmósfera):** backgrounds = el fondo como decisión (recoloreados, sin romper AA).
- **Componentes / animations:** UI con motion y microinteracciones — casi siempre fuera de la operación densa (P1).
- **⚠ TREND-RISK (Decay Test):** efectos "del año" (aurora/gradiente/glass/cursor-follow) que
  homogeneizan y envejecen. Usables, pero recoloreados y con criterio; declarar el riesgo si el ciclo es corto.
- **⚠ PERF/A11Y:** canvas/WebGL/rAF pesado o cursor-follow → pausar fuera de viewport, respetar reduced-motion, cuidar LCP/INP.

---

## 1. TEXT ANIMATIONS (23) — candidatos a R2 (momento-firma del headline)
`ASCIIText` · `BlurText` · `CircularText` · `CountUp` · `CurvedLoop` · `DecryptedText` ·
`FallingText` · `FuzzyText` · `GlitchText` · `GradientText` · `RotatingText` · `ScrambledText` ·
`ScrollFloat` · `ScrollReveal` · `ScrollVelocity` · `ShinyText` · `Shuffle` · `SplitText` ·
`TextCursor` · `TextPressure` · `TextType` · `TrueFocus` · `VariableProximity`

- **Calmos / sobrios (Protector, direcciones editoriales):** `BlurText`, `SplitText`, `ScrollReveal`, `ScrollFloat`, `CountUp` (para un número-dato).
- **Expresivos / con carácter fuerte:** `VariableProximity`, `TextPressure`, `TrueFocus`, `RotatingText`, `CurvedLoop`, `ShinyText`.
- **Nicho / temáticos (usar solo si el mundo de la dirección lo pide):** `ASCIIText`, `GlitchText`, `DecryptedText`, `ScrambledText`, `FuzzyText`, `TextType` (retro/terminal/tech). ⚠ TREND-RISK: `GradientText` (gradiente default).

## 2. BACKGROUNDS (45) — candidatos a R1 (atmósfera del fondo)
`Aurora` · `Balatro` · `Ballpit` · `Beams` · `ColorBends` · `DarkVeil` · `Dither` · `DotField` ·
`DotGrid` · `EvilEye` · `FaultyTerminal` · `Ferrofluid` · `FloatingLines` · `Galaxy` ·
`GradientBlinds` · `Grainient` · `GridDistortion` · `GridMotion` · `GridScan` · `Hyperspeed` ·
`Iridescence` · `LetterGlitch` · `LightPillar` · `LightRays` · `Lightfall` · `Lightning` ·
`LineWaves` · `LiquidChrome` · `LiquidEther` · `Orb` · `Particles` · `PixelBlast` · `PixelSnow` ·
`Plasma` · `PlasmaWave` · `Prism` · `PrismaticBurst` · `Radar` · `RippleGrid` · `ShapeGrid` ·
`SideRays` · `Silk` · `SoftAurora` · `Threads` · `Waves`

- **Sobrios / editoriales (sirven a paletas cálidas/calmas sin gritar):** `Grainient` (grano),
  `Silk`, `Threads`, `LineWaves`, `Waves`, `FloatingLines`, `DotGrid`, `DotField`, `SoftAurora` (aurora atenuada), `Beams`, `LightRays`/`LightPillar`/`Lightfall` (luz localizada = R1 clásico).
- **⚠ TREND-RISK (homogeneizan / "showcase de IA"):** `Aurora`, `Iridescence`, `LiquidChrome`,
  `LiquidEther`, `Plasma`/`PlasmaWave`, `Prism`/`PrismaticBurst`, `GradientBlinds`, `Balatro`, `Orb`.
  Usables solo recoloreados a la paleta del proyecto y con criterio; casi nunca en marcas sobrias.
- **Temáticos (retro/tech/espacial — solo si el mundo lo pide):** `FaultyTerminal`, `LetterGlitch`,
  `Hyperspeed`, `Galaxy`, `Radar`, `GridScan`, `Dither`, `PixelBlast`/`PixelSnow`.
- **⚠ PERF pesado (WebGL/canvas):** `Ballpit`, `Ferrofluid`, `LiquidChrome/Ether`, `Galaxy`,
  `Hyperspeed`, `Particles`, `Prism*`, `Plasma*` → pausar fuera de viewport, medir INP/LCP, no en mobile de gama baja sin fallback.

## 3. COMPONENTS (37) — UI con motion (fuera de la operación densa por default, P1)
`AnimatedList` · `BorderGlow` · `BounceCards` · `BubbleMenu` · `CardNav` · `CardSwap` · `Carousel` ·
`ChromaGrid` · `CircularGallery` · `Counter` · `DecayCard` · `Dock` · `DomeGallery` · `ElasticSlider` ·
`FlowingMenu` · `FluidGlass` · `FlyingPosters` · `Folder` · `GlassIcons` · `GlassSurface` · `GooeyNav` ·
`InfiniteMenu` · `Lanyard` · `LineSidebar` · `MagicBento` · `Masonry` · `ModelViewer` · `PillNav` ·
`PixelCard` · `ProfileCard` · `ReflectiveCard` · `ScrollStack` · `SpotlightCard` · `Stack` ·
`StaggeredMenu` · `Stepper` · `TiltedCard`

- **Navegación:** `CardNav`, `PillNav`, `GooeyNav`, `StaggeredMenu`, `BubbleMenu`, `FlowingMenu`, `Dock`, `LineSidebar`.
- **Cards / galería (portfolio, showcase):** `SpotlightCard`, `TiltedCard`, `ChromaGrid`, `Masonry`,
  `CircularGallery`, `DomeGallery`, `FlyingPosters`, `BounceCards`, `CardSwap`, `Stack`, `Carousel`, `ProfileCard`, `DecayCard`, `PixelCard`.
- **Utilitarios con motion (pueden entrar a producto con criterio):** `Stepper` (onboarding), `AnimatedList`, `Counter`, `ElasticSlider`, `Folder`.
- **⚠ TREND-RISK (glassmorphism/gimmick):** `GlassSurface`, `GlassIcons`, `FluidGlass`, `MagicBento`, `Lanyard`, `ReflectiveCard`.
- **⚠ PERF/dep pesada:** `ModelViewer` (3D), `Lanyard`, `FlyingPosters`, `DomeGallery`.

## 4. ANIMATIONS (30) — microinteracciones / efectos (cuentagotas; cuidado en producto)
`AnimatedContent` · `Antigravity` · `BlobCursor` · `ClickSpark` · `Crosshair` · `Cubes` ·
`ElectricBorder` · `FadeContent` · `GhostCursor` · `GlareHover` · `GradualBlur` · `ImageTrail` ·
`LaserFlow` · `LogoLoop` · `MagicRings` · `Magnet` · `MagnetLines` · `MetaBalls` · `MetallicPaint` ·
`Noise` · `OrbitImages` · `PixelTrail` · `PixelTransition` · `Ribbons` · `ShapeBlur` · `SplashCursor` ·
`StarBorder` · `StickerPeel` · `Strands` · `TargetCursor`

- **Reveals sobrios (utilitarios, sirven a cualquier dirección):** `AnimatedContent`, `FadeContent`, `GradualBlur`, `LogoLoop` (marquee de logos).
- **Realces puntuales:** `GlareHover`, `StarBorder`, `ElectricBorder`, `Magnet`/`MagnetLines`, `ClickSpark`, `PixelTransition`.
- **⚠ TREND-RISK / cursor-follow (homogeneizan y molestan en desktop-only):** `BlobCursor`,
  `GhostCursor`, `SplashCursor`, `TargetCursor`, `Crosshair`, `ImageTrail`, `PixelTrail`. Casi nunca en producto serio; jamás sin reduced-motion.
- **⚠ PERF pesado:** `MetaBalls`, `Ribbons`, `Strands`, `LaserFlow`, `MetallicPaint`, `Cubes`, `Antigravity`.

---

## Shortlist por intención (atajo de decisión)
- **Headline-firma calmo (editorial/producto/salud):** `BlurText`, `SplitText`, `ScrollReveal`, `ScrollFloat`.
- **Número que impacta (dato/proof):** `CountUp`, `Counter`.
- **Atmósfera sobria de fondo (marca cálida, no gritona):** `Grainient`, `Silk`, `Threads`, `LineWaves`, `LightRays`, `DotGrid`.
- **Portfolio/showcase con carácter:** `SpotlightCard`, `TiltedCard`, `ChromaGrid`, `CircularGallery`.
- **Onboarding con pasos:** `Stepper`.
- **EVITAR por default (trend/homogeneiza):** `Aurora`, `Iridescence`, `LiquidChrome`, gradient/glass*, cursores-follow. Solo con dirección que lo pida + recolor + Decay Test declarado.

## Reglas que se aplican SIEMPRE (de §5.1)
1 momento-firma por vista (P2) · superficie-marca, no operación densa (P1) · recolorear+retimear
a los tokens del proyecto (P4) · efecto DISTINTO por proyecto (anti-clon, P4) · reduced-motion +
fallback visible + AA + pausar canvas fuera de viewport (P5) · React-only (P6).
