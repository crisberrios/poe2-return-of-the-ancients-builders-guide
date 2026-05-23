+++
title = "Investigación de League Starter PoE 2 0.5 — Plan y Metodología"
+++

**Autor:** Claude (Cowork)
**Fecha:** 2026-05-22
**Objetivo:** Decidir un league starter para el parche **0.5 "Return of the Ancients"** identificando qué ascendencias son las más poderosas, las más buffeadas y las más nerfeadas.

---

## 1. Contexto

- **Parche bajo estudio:** 0.5.0 "Return of the Ancients" — la liga se lanza el 2026-05-29.
- **Liga:** Runes of Aldur.
- **Parche de comparación:** 0.4 "The Last of the Druids" (parche mayor anterior).
- **Contenido nuevo (ignorado por instrucciones del usuario):** mecánica de liga Runes of Aldur, currency Verisium/runeforging, Lineage Supports únicas a las nuevas runas y rework del árbol de Atlas ("Origins of Divinity"). El usuario también pidió ignorar las **nuevas runas**.
- **Lo que SÍ investigamos:** cambios de ascendencia, cambios del árbol de pasivas, cambios de gemas de habilidad/asistencia, cambios de objetos que afectan a habilidades existentes (las mecánicas estructurales que deciden el poder de las builds), y las dos ascendencias nuevas (Artista Marcial, Caminante Espiritual) porque son nuevas opciones de build.

---

## 2. Fuentes (validadas durante el PoC de Guerrero)

| Fuente | Qué nos da | Estado | Notas |
| --- | --- | --- | --- |
| **forum de pathofexile.com (notes 0.5.0)** | Patch notes oficiales y autoritativas | OK — Fetched y parseado a `patch_notes_0_5_0_sections/` (10 archivos de sección) | Fuente de verdad para cada cambio. |
| **poe2.ninja** | Datos de ladder de top builds — conteo de personajes, popularidad de gemas de habilidad, picks del árbol de pasivas | Atención — Client-rendered; **WebFetch devuelve body vacío**. No se puede acceder sin Chrome browser MCP (ninguno conectado) o que el usuario haga copy-paste de páginas clave. | Esta es nuestra señal de popularidad más autoritativa pero actualmente inaccesible. Workaround: extraer datos de artículos que citan poe.ninja, o que el usuario pegue los datos más adelante. |
| **mobalytics.gg** | Tier list editorial + guías de build por ascendencia | OK — Tier list accesible (lo suficientemente server-rendered). **Actualmente todavía con la tier list de predicciones de 0.4** — no han publicado la tier list de 0.5 todavía (la liga se lanza el 2026-05-29). Las páginas de build por ascendencia existen. | Se va a refrescar en los próximos días. Por ahora: usar la lista de 0.4 como baseline + comentario de creadores. |
| **poe2db.tw** | Cada nodo pasivo de ascendencia, gema de habilidad, gema de asistencia, objeto único — con el texto actual de 0.5 | OK — Server-rendered, accesible vía WebFetch. Confirmado 17 nodos de Titán, ambas ascendencias nuevas de 0.5 presentes. | **Cross-reference primario** para convertir "el parche nerfeó el notable X" en "esto afecta a las builds Y, Z." |
| **Artículos de tier-list 0.5 de terceros (aoeah.com, iggm.com)** | Tier list patch-note-driven específica para 0.5 | OK — Fetched. La calidad es incierta (agregadores de contenido, no creadores top) — tratar como una *señal*, verificar contra patch notes. | Útiles porque salieron hoy mismo cubriendo ya 0.5. |
| **maxroll.gg/poe2/meta** | Página de meta de builds | Atención — Client-rendered; body vacío. | Saltar a menos que haya Chrome browser disponible. |
| **poe2.dev/builds** | Agregador de estadísticas de top-1000 del ladder | Atención — Client-rendered; body vacío. | Saltar a menos que haya Chrome browser disponible. |

### Caveat crítico — actualidad de los datos

La liga se lanza el **2026-05-29**. Implicancias:
- **Los datos de popularidad de poe2.ninja van a estar dispersos durante ~1 semana.** La mayoría de los personajes tempranos estarán en lvl 1–60, no en endgame. La distribución de builds va a sesgarse hacia habilidades de leveling rápido, no hacia la meta eventual de mapping/jefes.
- **La tier list de Mobalytics todavía es de predicciones de 0.4.** Su lista de 0.5 va a salir en los próximos días, escrita por Jungroan / Ruetoo / Fubgun / Ben.
- Deberíamos **marcar todo ranking como preliminar** y planear re-correr la investigación después de la semana 1 de la liga.

---

## 3. Lista confirmada de ascendencias (PoE 2 0.5)

Desde la nav de poe2db.tw + sección "New Content" de patch notes:

| Clase | Ascendencias | ¿Nueva en 0.5? |
| --- | --- | --- |
| Guerrero | Titán, Adalid de guerra, Herrero de Kitava | No |
| Exploradora | Tiradora, Rastreadora | No |
| Cazadora | Amazona, Ritualista, **Caminante Espiritual** | Caminante Espiritual = NUEVA |
| Bruja | Infernalista, Maga de sangre, Liche, Liche abisal | No |
| Hechicera | Tejetormentas, Cronomante, Discípula de Varashta | No |
| Mercenario | Estratega, Cazador de brujas, Legionario gemita | No |
| Druida | Oráculo, Chamán | No |
| Monje | Invocador, Acólito de Chayula, **Artista Marcial** | Artista Marcial = NUEVA |

Total: **23 ascendencias** en 8 clases. Vamos a producir **8 archivos de ascendencia por clase** (uno .md por clase agrupando todas sus ascendencias) O **23 archivos** (uno por ascendencia). Recomiendo el split por clase (8 archivos) ya que las builds suelen compartir impactos del parche dentro de una clase — confirmar con el usuario.

---

## 4. Plantilla del archivo de investigación por clase

Cada `<clase>.md` contiene, por ascendencia:

```
# <Ascendencia>
## Identidad
- Clase, rol (ej. melee tanque, caster glass-cannon)
- Notables definitorios de la ascendencia (con links a poe2db)

## Top builds (0.4 → 0.5)
- Para cada top build: habilidad, supports clave, clusters clave del árbol pasivo, únicos clave
- Fuente(s): páginas de build de mobalytics, samples PoB de ninja, nombres de creadores

## Impacto del parche 0.5
| Cambio | Sección fuente | ¿Afecta a esta ascendencia? | Dirección | Magnitud (S/M/L) | Notas |
| --- | --- | --- | --- | --- | --- |
| (una fila por cada cambio del parche relevante) | | | + buff / − nerf / ~ neutral | | |

## Veredicto neto
- Banda de poder antes de 0.5 / después de 0.5 (S/A/B/C/D/F)
- Buffeado por: ...
- Nerfeado por: ...
- Viabilidad como league-start: ...
```

## 5. Rúbrica de rating de impacto

Para cada línea del parche × ascendencia, rankear:

- **Dirección:** buff (+), nerf (−), neutral (~), o nuevo (★).
- **Magnitud:**
  - **L (grande):** cambia la palanca core de daño/defensa de la build (ej. rework de Pacto Vaal, caps de leech, nerf a Overwhelming Toxicity de Rastreadora).
  - **M (mediana):** tuning notable a una habilidad o notable de uso frecuente (ej. nerf a la calidad de Triturahuesos, buff a la réplica de Terremoto).
  - **S (chica):** edge case o QoL (ej. update de animación, cambio solo de descripción).

El veredicto final por ascendencia combina:
1. **Señal de ranking:** tier de mobalytics (cuando publique la lista de 0.5) + artículos de tier de terceros + mi juicio.
2. **Señal de popularidad:** share de personajes/habilidades de poe2.ninja (cuando esté accesible).
3. **Señal de magnitud del parche:** suma de deltas L/M/S, ponderados (+1 / +0,3 / +0,1 por buff, espejado para nerfs).

---

## 6. Hallazgos de validación del PoC de Guerrero

Estas son las cosas que verifiqué específicamente para confirmar que el plan funciona *antes* de escalar:

1. **Las patch notes parsean limpio en 10 secciones.** Player / New Content / Ascendancy / Passive Tree / Skill / Support / Unique Item / Item / Monster / Bug Fixes. La sección de Cambios de Ascendencia *solo cambia 6 ascendencias* (Acólito de Chayula, Maga de sangre, Cronomante, Legionario gemita, Rastreadora, Cazador de brujas) — **las ascendencias del Guerrero no recibieron cambios directos en nodos de ascendencia**. El impacto para Guerrero llega enteramente vía cambios de habilidades / asistencias / objetos / árbol pasivo.
2. **poe2db.tw enumera limpiamente los 17 nodos de ascendencia del Titán.** Confirma que podemos mapear cada referencia de las patch notes (ej. "Notable Pasivo Potenciación Ancestral") a un nodo concreto.
3. **Cambios de habilidades relevantes para el Guerrero en 0.5:**
   - Embate rodante: nerf grande (− L) — primer slam 90→75%, segundo slam 180→150% base, tiempo de ataque +1.0s en vez de +1.5s (compensación parcial).
   - Terremoto: buff (+ M) — réplica 160→184% a 580→666% en gem 1–20.
   - Triturahuesos: nerf chico (− S) — calidad 30→20% velocidad de ataque incrementada.
   - Tótem de guerrero ancestral: cambio de claridad/QoL (~).
   - Grito fortalecedor: nerf (− M) — shockwave por muro de escudos limitada.
   - Muro de escudos / Escudo resonante / Magma Barrier: nerf chico (− S) — daño físico por 15 armadura 6→5 base.
   - Supercharged Slam: solo descripción (~).
4. **Cambios de objetos / únicos relevantes para el Guerrero:**
   - Arma de Ataque a Dos Manos: +Nivel a todas las Habilidades de Cuerpo a Cuerpo ahora +5 en T1 (era +7) — **− L para Guerreros melee de dos manos**, especialmente builds de slam de Titán que se apoyan en +nivel.
   - Maza de una mano rango base +0,1m (~ neutral, leve buff a clearing).
   - Modificador Bonded en guantes: warcry CDR 25% (era 15%) — **+ M para Adalid de guerra**.
   - Maza única Chober Chaber: ahora +2-3 a todas las habilidades de esbirros — relevante para crossovers warrior-minion (el Herrero de Kitava puede usar esta).
   - Stone Runes en Armas Marciales: 20/25/30 → 20/30/40% acumulación de stun — **+ S para Guerrero stun-focused**.
   - Soul Mantle ya no tiene −20-30% Vida de Tótem, ahora +75 Spirit — relevante para Guerreros de tótem (mayormente Herrero).
5. **Cambios del árbol pasivo relevantes para el Guerrero:**
   - **Punto clave Vínculo Ancestral reworkeado:** colocar tótems ya no cuesta/usa cargas; reserva 75 de spirit cada uno; **duplica el límite de tótems en vez de removerlo**. Esto es un **+ L** para builds de tótem-Guerrero (Herrero especialmente).
   - Pasivas pequeñas de bandera nerfeadas levemente (12→15% antes, ahora 12% — esperá, esto está al revés en el texto crudo; hay que doble-checkear). Afecta a builds Guerrero de War Banner / Defiance / Dread Banner.
   - Notable Cornado: ya no 40% phys, ahora 3% vida máxima + 20% leech — afecta a Guerreros melee/bleed. Leve + en tanquez, − en daño crudo.
   - Notable Voraz: ya no 20% instant leech, ahora 15% velocidad de ataque mientras hace leech — **− L para Adalid de guerra de Bleed** que dependía de grandes bursts de leech; mixto para todos los demás.
   - Múltiples nerfs relacionados con ES recharge — **irrelevantes para la mayoría de las builds de Guerrero** (los Guerreros corren armadura/vida, no ES).
6. **Cambio de Sangrado en Cambios de Jugador:**
   - "El daño de Sangrado sobre los jugadores ya no se incrementa al moverse" — pura defensa para jugadores (recibís menos daño de auto-sangrado al correr). **No afecta a los sangrados del lado-monstruo que infligen los Guerreros**.
7. **Veredicto de tier 0.5 de terceros (aoeah, tratar como una señal débil):**
   - **Titán: S Tier.** Core sin tocar (Forma descomunal, Potenciación ancestral). League-starter confiable.
   - **Adalid de guerra: A Tier.** Gritos de guerra infinitos, leveling fuerte, objetivo común de respec → Titán en el 41.
   - **Herrero de Kitava: A Tier (subió desde C).** Se beneficia enormemente del nuevo reforging Verisium (te permite mejorar únicos). Asalto giratorio y conversión siguen funcionales.

Todo esto se siente plausible dada la dirección del parche; el **salto del Herrero de C→A** es la afirmación más sorprendente y deberíamos tratarla con cuidado hasta que Mobalytics opine.

---

## 7. Preguntas abiertas para el usuario antes del lanzamiento a escala completa

1. **¿Un archivo por clase (8 archivos) o uno por ascendencia (23 archivos)?** Por-clase es más legible y agrupa mecánicas compartidas; por-ascendencia es más fácil de escanear al comparar.
2. **¿Debería intentar recuperar datos de poe2.ninja vía un Chrome browser conectado?** Actualmente no hay browser conectado. Sin él, falta la señal de popularidad. Opciones:
   - Esperar — vos conectás Chrome y yo scrapeo en la siguiente sesión.
   - Pegás los leaderboards clave de clase/habilidad de poe2.ninja en el chat.
   - Procedemos sin ninja y nos apoyamos en mobalytics + juicio del parche.
3. **¿Foco en Hardcore o Softcore?** Las tier lists divergen significativamente (ej. Adalid de guerra / Herrero / Invocador / Liche son S-tier en HC pero medios en SC). La lista de mobalytics asume SC/trade.
4. **¿Incluir las dos ascendencias nuevas (Caminante Espiritual, Artista Marcial) en la comparación?** Son completamente nuevas así que no van a existir datos de popularidad; el rating va a ser solo patch-note + tomas de creadores.

---

## 8. Orden propuesto de ejecución para la pasada completa de investigación

Una vez aprobado el plan, voy a ejecutar en este orden (en paralelo cuando sea posible):

1. Armar un `_patch_relevance_matrix.md` — cada línea del parche × cada ascendencia, puntuada una sola vez. Reutilizable por cada archivo por clase. Esto evita reevaluar el mismo cambio para cada ascendencia.
2. Archivos por clase en orden: Guerrero (ya draftado), Exploradora, Cazadora, Bruja, Hechicera, Mercenario, Druida, Monje.
3. `summary.md` final rankeando las 23 ascendencias por "más buffeada", "más nerfeada" y "poder al inicio de liga".

Esfuerzo estimado: ~1–2 horas de investigación + escritura para los 8 archivos de clase, asumiendo que la pregunta de datos de popularidad se resuelva.