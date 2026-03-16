---
name: business-model-brainstorming
version: 3.1.0
description: >
  This skill should be used when the user asks to "build a business model",
  "brainstorm a business idea", "create a business model canvas",
  "create my BMC", "build my BMC", "plan my startup",
  "validate my business idea", "define my value proposition",
  "validate my MVP", "design an experiment", "customer forces",
  "go-to-market plan", "unit economics", "revenue model",
  "hiring plan", "product roadmap", "pitch deck",
  "crea mi modelo de negocio", "planifica mi startup",
  "arma mi business model canvas", "valida mi idea",
  "/business-model-brainstorming", or wants guided help turning an idea
  into a structured business model covering the full startup lifecycle
  from problem validation through execution and acceleration.
---

# Lluvia de Ideas para Modelo de Negocio

Diálogo guiado interactivo para transformar una idea de negocio en un framework completo
de startup. Combina Running Lean (Maurya), Lean Canvas, metodología del Founder Institute
y Desarrollo de Realidad Sintética (SRD — Synthetic Reality Development) para cubrir
el ciclo de vida completo: Problema → Solución → Ejecución.

## Regla de idioma

Todo el contenido generado debe estar en **español**. Los términos de negocio se presentan
en formato **"español (English)"** la primera vez que aparecen, para que el emprendedor
aprenda la terminología en ambos idiomas. Después de la primera mención, se puede usar
el acrónimo solo. Nombres propios de frameworks y libros se mantienen en su idioma original.

## Modos de ejecución

### Modo normal (por defecto)
Escribe todos los entregables en `./business/`.

### Modo simulación (what-if)
Se activa cuando el usuario dice "simulación", "prueba", "what-if",
"no guardes nada", o agrega `--what-if` al comando.

En modo simulación:
- **NO** crear directorios ni escribir archivos
- **NO** usar las herramientas Write, Edit o Bash para creación de archivos
- **SÍ** recorrer todas las fases interactivamente (preguntas, puertas de aprobación)
- **SÍ** presentar el contenido completo de cada entregable en la conversación como bloque de código
- **SÍ** prefijar cada entregable con un encabezado mostrando qué SE ESCRIBIRÍA:

```
📋 [SIMULACIÓN] Se escribiría: ./business/01-problema-hipotesis/01-perfil-fundador.md
───────────────────────────────────────────────────────────────
[contenido completo aquí]
───────────────────────────────────────────────────────────────
```

- **SÍ** rastrear el progreso como si los archivos se hubieran escrito
- Al final, presentar un resumen de todos los archivos que SE HABRÍAN creado
- Ofrecer: "¿Querés que escriba todos estos archivos ahora? (sale del modo simulación)"

Si acepta, cambiar a modo normal y escribir todos los entregables acumulados de una vez.

### Detección del modo

Al INICIO de la sesión de brainstorming, buscar señales de simulación:
1. El usuario dice explícitamente "simulación", "what-if", "prueba", "--what-if"
2. El usuario dice "probemos con..." o "quiero probar" o "sin guardar"
3. Si no es claro, preguntar: "¿Querés que escriba los archivos o preferís modo simulación (sin guardar)?"

Anunciar el modo claramente:
- Normal: "📝 Modo normal — los archivos se guardarán en `./business/`"
- Simulación: "🔍 Modo simulación — nada se guarda, todo se muestra en la conversación"

## Directorio de salida (modo normal)

Todos los archivos van en `./business/` organizados en tres espacios numerados:

```
./business/
├── 01-problema-hipotesis/     # 5 entregables
├── 02-solucion-validacion/    # 16 entregables
├── 03-ejecucion-aceleracion/  # 10 entregables
├── README.md                  # Resumen del modelo de negocio
./README.md                    # README del proyecto (raíz)
```

## Puerta obligatoria

NO generar ningún entregable hasta que las preguntas de la fase correspondiente hayan sido
respondidas y el usuario haya aprobado la sección. Preguntar UNA A LA VEZ. Esperar respuesta.

## Vista general del proceso

Tres espacios, cada uno con una puerta de validación (Validation Gate) antes de avanzar.

```
ESPACIO 1: PROBLEMA-HIPÓTESIS (Fases 1-5)
  ├─ Fase 1: Perfil del Fundador      → 01-problema-hipotesis/01-perfil-fundador.md
  ├─ Fase 2: Validación del Problema  → 01-problema-hipotesis/02-entrevista-problema.md
  ├─ Fase 3: Perfil del Cliente       → 01-problema-hipotesis/03-perfil-expectativas-cliente.md
  ├─ Fase 4: Fuerzas del Cliente      → 01-problema-hipotesis/04-fuerzas-del-cliente.md
  ├─ Fase 5: Investigación de Mercado → 01-problema-hipotesis/05-investigacion-mercado.md
  └─ PUERTA 1: ¿El problema es real y suficientemente doloroso?

ESPACIO 2: SOLUCIÓN-VALIDACIÓN (Fases 6-8)
  ├─ Fase 6: Modelo de Negocio Canvas → 02-solucion-validacion/00 + 14 módulos
  ├─ Fase 7: Entrevista de Solución   → 02-solucion-validacion/15-entrevista-solucion.md
  ├─ Fase 8: Experimento MVP          → 02-solucion-validacion/16-experimento-mvp.md
  └─ PUERTA 2: ¿La solución resuelve el problema y alguien pagaría?

ESPACIO 3: EJECUCIÓN-ACELERACIÓN (Fases 9-18)
  ├─ Fase 9:  Modelo de Ingresos      → 03-ejecucion-aceleracion/01-modelo-de-ingresos.md
  ├─ Fase 10: Economía Unitaria       → 03-ejecucion-aceleracion/02-economia-unitaria.md
  ├─ Fase 11: Modelo Financiero       → 03-ejecucion-aceleracion/03-modelo-financiero.md
  ├─ Fase 12: Marca e Identidad       → 03-ejecucion-aceleracion/04-marca-e-identidad.md
  ├─ Fase 13: Fundación Legal         → 03-ejecucion-aceleracion/05-fundacion-legal.md
  ├─ Fase 14: Salida al Mercado       → 03-ejecucion-aceleracion/06-salida-al-mercado.md
  ├─ Fase 15: Hoja de Ruta del Producto → 03-ejecucion-aceleracion/07-hoja-de-ruta.md
  ├─ Fase 16: Equipo y Contratación   → 03-ejecucion-aceleracion/08-equipo-y-contratacion.md
  ├─ Fase 17: Junta Asesora           → 03-ejecucion-aceleracion/09-junta-asesora.md
  ├─ Fase 18: Presentación a Inversores → 03-ejecucion-aceleracion/10-pitch-deck.md
  └─ PUERTA 3: ¿La startup está lista para escalar?

EMPAQUETADO
  Fase 19: README del Negocio         → business/README.md
  Fase 20: README del Proyecto        → README.md (raíz)
  Fase 21: Integración SRD            → ofrece /srd-framework:srd-assess
```

---

## ESPACIO 1: PROBLEMA-HIPÓTESIS

### Fase 1: Perfil del Fundador (Founder Profile) — 3-4 preguntas

Leer plantilla: `assets/templates/founder-profile.md`

El perfil del fundador usa formato de README de perfil de GitHub con insignias (badges)
de shields.io, secciones con emojis, línea del tiempo profesional, portafolio de startups
y visualización de habilidades.

**PF-1 — Tu por qué**: "¿Por qué estás emprendiendo? Describí cómo será tu vida en 3-5 años
si lanzás tu empresa vs si dejás de emprender."

**PF-2 — Historia y trayectoria**: "Contame brevemente tu historia en 5 puntos:
infancia, formación, carrera, emprendimiento y visión del futuro.
¿Qué startups o proyectos previos tenés? ¿Logros cuantificables?"

**PF-3 — Habilidades y calificación única**: "¿Cuáles son tus habilidades técnicas y blandas
principales? ¿Por qué estás únicamente calificado/a para resolver este problema?"

**PF-4 — Tiempo, metas y enlaces**: "¿Cuántas horas semanales podés dedicarle? ¿Metas principales?
Pasame tus enlaces: LinkedIn, GitHub, portafolio, redes sociales."

Generar `01-problema-hipotesis/01-perfil-fundador.md` con insignias de shields.io para
habilidades, línea del tiempo profesional, portafolio de startups y todas las secciones
de la plantilla. Presentar. Esperar aprobación.

### Fase 2: Validación del Problema (Problem Validation) — 4-6 preguntas

Leer plantilla: `assets/templates/entrevista-problema.md`

Explorar el problema usando los 4 componentes de Running Lean:
Detonante, Frecuencia, Relevancia, Viabilidad Técnica.

**Siempre Opción B**: Reemplazar TODOS los marcadores genéricos con contexto del proyecto.

Generar `01-problema-hipotesis/02-entrevista-problema.md`. Presentar. Esperar aprobación.

### Fase 3: Perfil del Cliente (Customer Profile) — 4-6 preguntas

Leer plantilla: `assets/templates/perfil-expectativas-cliente.md`

Cubrir: Demografía, Ikigai, Dolores y Ganancias (Pains/Gains), Trabajos por Hacer del
Cliente (JTBD — Jobs-to-be-Done) con dimensiones de complejidad (📗🧠💪🛠️💸🌱).
Poblar las secciones 6-12 con respuestas de la Fase 2 — no volver a preguntar.

**Regla de contextualización de las Dimensiones de Complejidad (Opción B)**:
Las 6 dimensiones de complejidad NO deben presentarse como preguntas genéricas abstractas.
Antes de preguntar, explicar al usuario para qué sirven y en qué contexto responderlas:

1. Introducir con: "Queremos entender **qué tan difícil es para vos [el trabajo/proceso
   específico identificado en el JTBD]** — desde [inicio del proceso] hasta [fin del proceso]."
2. Cada nivel de cada dimensión debe reescribirse con el contexto del proyecto:
   - Genérico: "Necesito herramientas especializadas disponibles en el mercado"
   - Contextualizado: "Necesité documentos especiales (cartas de referencia, comprobantes)"
3. Las descripciones de cada nivel deben usar el lenguaje del usuario, no jerga de frameworks.
4. Incluir el indicador numérico `(X/5)` junto a los emojis para accesibilidad en terminales.

Generar `01-problema-hipotesis/03-perfil-expectativas-cliente.md`. Presentar. Esperar aprobación.

### Fase 4: Fuerzas del Cliente (Customer Forces) — 3-4 preguntas

Leer plantilla: `assets/templates/fuerzas-del-cliente.md`

Mapear las 4 fuerzas de Ash Maurya: Empuje (Push), Atracción (Pull),
Ansiedad (Anxiety) e Inercia (Inertia). Calcular el balance.

Generar `01-problema-hipotesis/04-fuerzas-del-cliente.md`. Presentar. Esperar aprobación.

### Fase 5: Investigación de Mercado (Market Research) — 3-4 preguntas + agente automático

Al iniciar esta fase, lanzar automáticamente un agente de investigación en segundo plano
(Agent tool, `run_in_background: true`) con el siguiente prompt adaptado al proyecto:

```
Investigar el mercado de [industria/sector] en [país/región]. Necesito:
1. TODAS las plataformas/alternativas que la gente usa para [resolver el problema].
2. Startups fallidas que intentaron resolver esto en [región] y por qué fracasaron.
3. Tamaño de mercado: hogares/usuarios, TAM, SAM, SOM con datos reales y fuentes.
4. Análisis de competidores clave con fortalezas y debilidades.
Buscar en español e inglés. Retornar hallazgos con fuentes/URLs.
```

Mientras el agente investiga, hacer las preguntas complementarias al usuario:

**IM-1**: "¿Conocés competidores directos? Si tenés URLs, pasámelas para analizarlos
con Chrome DevTools (capturas de pantalla + análisis de la interfaz en tiempo real)."

Si el usuario proporciona URLs de competidores, usar Chrome DevTools MCP
(`navigate_page` + `take_screenshot` + `take_snapshot`) para analizar la interfaz,
funcionalidades, precios y debilidades del competidor con datos reales.

**IM-2**: "¿Conocés startups que hayan intentado resolver esto y fracasaron? ¿Por qué fallaron?"

**IM-3**: "¿Quiénes son tus 3-5 Clientes Líderes (Lead Customers) — personas que mostraron
más dolor y disposición a pagar?"

Cuando el agente de investigación termine, combinar sus hallazgos con las respuestas del
usuario para generar `01-problema-hipotesis/05-investigacion-mercado.md`.
Presentar. Esperar aprobación.

### PUERTA 1

Presentar resumen y preguntar:
> "Espacio 1 completo. Antes de pasar a diseñar la solución, validemos:
> - ¿Las Fuerzas del Cliente tienen balance positivo?
> - ¿Hay evidencia de que el problema es real (entrevistas, datos)?
> - ¿El mercado es suficientemente grande?
> ¿Avanzamos al Espacio 2 o necesitamos ajustar algo?"

---

## ESPACIO 2: SOLUCIÓN-VALIDACIÓN

### Fase 6: Modelo de Negocio Canvas (BMC — Business Model Canvas) — 5 rondas de preguntas

Generar 15 archivos en `02-solucion-validacion/` (00 índice + 14 módulos).
Agrupar preguntas en 5 rondas según `references/methodology.md`.

Para el módulo 13 (Métricas de Impacto), incorporar el Sistema de Métricas de Impacto
(IRIS+ — Impact Reporting and Investment Standards) cuando aplique.

### Fase 7: Entrevista de la Solución (Solution Interview) — 2-3 preguntas

Leer plantilla: `assets/templates/entrevista-solucion.md`

Generar `02-solucion-validacion/15-entrevista-solucion.md`. Presentar. Esperar aprobación.

### Fase 8: Experimento con Producto Mínimo Viable (MVP — Minimum Viable Product) — 3-4 preguntas

Leer plantilla: `assets/templates/experimento-mvp.md`

Generar `02-solucion-validacion/16-experimento-mvp.md`. Presentar. Esperar aprobación.

### PUERTA 2

> "Espacio 2 completo. Antes de pasar a ejecución:
> - ¿La Entrevista de la Solución mostró compromiso financiero (no solo verbal)?
> - ¿El experimento MVP confirmó la hipótesis principal?
> - ¿El BMC es internamente consistente?
> ¿Avanzamos al Espacio 3?"

---

## ESPACIO 3: EJECUCIÓN-ACELERACIÓN

### Fase 9: Modelo de Ingresos (Revenue Model) — 3-4 preguntas

**MI-1**: "Investigá 3 modelos de ingresos que usen tus competidores. ¿Cuáles son y cómo
los mejorarías?"

**MI-2**: "De esos 3 modelos, ¿cuáles 2 querés testear? Para cada uno, definí 2 puntos
de precio (price points): uno competitivo y otro que genere $1M en 18 meses."

**MI-3**: "Describí los Pasos hacia el Ingreso (Steps to Revenue): ¿cuáles son todos
los pasos desde que un prospecto te conoce hasta que depositás dinero en tu cuenta?"

Generar `03-ejecucion-aceleracion/01-modelo-de-ingresos.md`. Presentar. Esperar aprobación.

### Fase 10: Economía Unitaria (Unit Economics) — 2-3 preguntas

**EU-1**: "¿Cuánto te cuesta adquirir un cliente — Costo de Adquisición (CAC — Customer
Acquisition Cost)? Incluí todos los costos: marketing, ventas, incorporación."

**EU-2**: "¿Cuánto vale un cliente a lo largo de su vida — Valor de Vida del Cliente
(LTV — Lifetime Value)? ¿Cuál es tu tasa de abandono (Churn Rate) estimada y tu
ticket promedio?"

**EU-3**: "¿Cuáles son tus 3 canales de adquisición principales?
¿Cuál tiene mejor tasa de conversión (Conversion Rate)?"

Generar `03-ejecucion-aceleracion/02-economia-unitaria.md`. Presentar. Esperar aprobación.

### Fase 11: Modelo Financiero (Financial Model) — 2-3 preguntas

**MF-1**: "¿Cuáles son tus costos fijos y variables mensuales?
(equipo, infraestructura, herramientas, servicios)"

**MF-2**: "¿Cuánto tiempo podés sobrevivir sin ingresos?
(ahorros, gastos personales, ingresos alternativos)"

**MF-3**: "¿Necesitás levantar capital? Si sí, ¿cuánto y de dónde?
  a) Autofinanciamiento (Bootstrapping — financiar con recursos propios sin inversores externos)
  b) Familia y amigos (Friends & Family Round)
  c) Ángeles inversores (Angel Investors)
  d) Capital de riesgo (VC — Venture Capital)
  e) Subvenciones o premios (Grants)"

Generar `03-ejecucion-aceleracion/03-modelo-financiero.md`. Presentar. Esperar aprobación.

### Fase 12: Marca e Identidad (Branding) — 2-3 preguntas

**MI-1**: "Listá 10+ palabras que evoquen tu producto, cliente, problema y emociones deseadas."

**MI-2**: "¿Ya tenés nombre? Si no, ¿tenés candidatos? Verificaremos dominio y redes."

**MI-3**: "¿Qué elementos de diseño necesitás? (logotipo, tarjetas, página de aterrizaje,
plantilla de presentación)"

Generar `03-ejecucion-aceleracion/04-marca-e-identidad.md`. Presentar. Esperar aprobación.

### Fase 13: Fundación Legal (Legal Foundation) — 2-3 preguntas

**FL-1**: "¿Ya estás constituido? ¿Qué tipo de entidad? ¿En qué jurisdicción?"

**FL-2**: "¿Tenés cofundadores? ¿Cómo es la distribución de participación accionaria (equity)?"

**FL-3**: "¿Qué acuerdos legales necesitás? (Acuerdo de Confidencialidad (NDA — Non-Disclosure Agreement), Cesión de
Propiedad Intelectual (IP Assignment), contrato laboral, Acuerdo Estándar de Asesores
del Founder Institute (FAST — Founder Advisor Standard Template))"

Generar `03-ejecucion-aceleracion/05-fundacion-legal.md`. Presentar. Esperar aprobación.

### Fase 14: Salida al Mercado (Go-to-Market) — 2-3 preguntas

**SM-1**: "¿Cuáles son tus 5 canales de adquisición candidatos?
(redes sociales, contenido, publicidad pagada, relaciones públicas, ventas directas,
afiliados, eventos)"

**SM-2**: "Escribí 3 mensajes de marketing de ≤140 caracteres para tu solución."

**SM-3**: "¿Qué herramientas de marketing vas a usar? (analítica, correo, pruebas A/B)"

Generar `03-ejecucion-aceleracion/06-salida-al-mercado.md`. Presentar. Esperar aprobación.

### Fase 15: Hoja de Ruta del Producto (Product Roadmap) — 2-3 preguntas

**HR-1**: "¿Cuáles son tus 3 metas de la solución (Solution Goals) para el próximo año?
(medibles y concretas)"

**HR-2**: "Listá todas las funcionalidades (features) que necesitás. Para cada una indicá:
prioridad (1=esencial, 2=siguiente, 3=deseable) y versión de lanzamiento (Beta, v1.0, v2.0)."

**HR-3**: "¿Cuál es tu plan de lanzamientos (releases)?
(cada ~2 semanas, cada lanzamiento valida 1 hipótesis)"

Generar `03-ejecucion-aceleracion/07-hoja-de-ruta.md`. Presentar. Esperar aprobación.

### Fase 16: Equipo y Contratación (Team & Hiring) — 2-3 preguntas

**EC-1**: "¿Qué roles necesitás para ejecutar tu hoja de ruta?
¿Cuáles son internos y cuáles tercerizados (outsourced)?"

**EC-2**: "¿Cuál es tu plan de contratación (Hiring Plan) para los próximos 18 meses?
(rol, cuándo, compensación, participación accionaria)"

**EC-3**: "¿Cuáles son los 5-7 valores de tu empresa? (código de ética)"

Generar `03-ejecucion-aceleracion/08-equipo-y-contratacion.md`. Presentar. Esperar aprobación.

### Fase 17: Junta Asesora (Advisory Board) — 2-3 preguntas

**JA-1**: "Necesitás 3 asesores en 3 categorías: Startup (con salida exitosa — exit),
Industria (experto en el dominio) y Tecnología/Marketing. ¿Tenés candidatos?"

**JA-2**: "¿Conocés conectores que puedan presentarte a estos asesores?"

**JA-3**: "¿Conocés el FAST para compensar asesores con participación accionaria?"

Generar `03-ejecucion-aceleracion/09-junta-asesora.md`. Presentar. Esperar aprobación.

### Fase 18: Presentación a Inversores (Pitch Deck) — 2-3 preguntas

Leer plantilla: `assets/templates/pitch-deck-marp.md`

Versión lista para inversores: incorporar TODO el contexto de los Espacios 1-3.
Reemplazar año y nombre de empresa codificados en la plantilla con valores reales.

Generar `03-ejecucion-aceleracion/10-pitch-deck.md`. Presentar. Esperar aprobación.

### PUERTA 3

> "Espacio 3 completo. Lista de verificación para escalar (scale-up readiness):
> - ¿Economía unitaria viable (LTV > 3× CAC)?
> - ¿Modelo financiero con camino a la rentabilidad?
> - ¿Fundación legal establecida?
> - ¿Equipo con roles clave cubiertos?
> - ¿Junta asesora conformada?
> - ¿Presentación lista para inversores?"

---

## EMPAQUETADO (Fases 19-21)

### Fase 19: README del Negocio
Generar `business/README.md` con enlaces a los 3 espacios y estado de avance.

### Fase 20: README del Proyecto
Generar `README.md` en la raíz del proyecto siguiendo `references/readme-guide.md`.

### Fase 21: Integración SRD
Ofrecer `/srd-framework:srd-assess` con contexto precargado de todos los archivos de negocio.

---

## Principios clave

- **Una pregunta a la vez** — nunca abrumar con múltiples preguntas
- **Opción múltiple cuando sea posible** — más fácil de responder; abierta cuando sea necesario
- **Siempre Opción B** — personalizar cada marcador genérico con contexto del proyecto
- **Puertas de aprobación** — presentar cada entregable, esperar aprobación antes de avanzar
- **Puertas de validación** — verificar antes de avanzar entre espacios
- **Problema antes que Solución antes que Ejecución** — nunca saltar espacios
- **Español como base** — con términos de negocio en formato "español (English)" la primera vez
- **Diagramas en Mermaid** — todo diagrama de flujo, máquina de estados, arquitectura o
  secuencia debe usar sintaxis Mermaid (```mermaid). No usar ASCII art ni diagramas de texto.

## Recursos adicionales

### Archivos de referencia
- **`references/methodology.md`** — Bancos de preguntas detallados, reglas de personalización
- **`references/output-structure.md`** — Estructura de directorios, detalles de archivos, puertas de validación
- **`references/readme-guide.md`** — Patrones de generación de README

### Archivos de plantilla (leer antes de generar)
- **`founder-profile.md`** — Perfil del fundador estilo GitHub con insignias, línea del tiempo, portafolio
- **`entrevista-problema.md`** — Entrevista del problema (7 secciones)
- **`perfil-expectativas-cliente.md`** — Perfil del cliente con JTBD (Jobs-to-be-Done) + 📗🧠💪🛠️💸🌱
- **`fuerzas-del-cliente.md`** — Diagrama de las 4 fuerzas del cliente
- **`entrevista-solucion.md`** — Entrevista de la solución + escalera de compromiso
- **`experimento-mvp.md`** — Ciclo de experimento MVP
- **`pitch-deck-marp.md`** — Presentación MARP (Markdown Presentation Ecosystem, 12 diapositivas)
