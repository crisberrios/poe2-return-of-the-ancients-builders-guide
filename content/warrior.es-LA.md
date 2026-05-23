+++
title = "Guerrero — Investigación PoE 2 0.5 (PoC)"
+++

**Parche:** 0.5.0 "Return of the Ancients" (2026-05-29)
**Comparado con:** 0.4 "The Last of the Druids"
**Estado:** Proof-of-concept — valida la metodología antes de escalar a las 8 clases.

---

## Clase Guerrero — overview

Tres ascendencias, todas construidas alrededor de fuerza/mazas a dos manos/escudos/gritos de guerra:

- **Titán** — potencia genérica de fuerza/slam. "Hacer que los números chicos sean grandes."
- **Adalid de guerra** — tótems, gritos de guerra, sangrado, tanquez.
- **Herrero de Kitava** — armour-break, conversión de armas (frío/fuego), esbirro Manifest Weapon.

Según las patch notes oficiales de 0.5, **ninguna de estas tres ascendencias recibió cambios directos de nodo** en la sección de Cambios de Ascendencia. Las únicas ascendencias tocadas en esa sección son: Acólito de Chayula, Maga de sangre, Cronomante, Legionario gemita, Rastreadora y Cazador de brujas. Así que el impacto sobre Guerrero llega enteramente vía *habilidades, gemas de asistencia, árbol de pasivas, objetos y cambios de mecánicas de jugador*.

---

## Cómo el parche 0.5 afecta a los Guerreros (matriz)

Dirección: **+** buff · **−** nerf · **~** neutral / solo descripción · **★** nuevo. Magnitud: **L/M/S** = large/medium/small (grande/mediano/chico).

| # | Cambio | Sección fuente | Titán | Adalid de guerra | Herrero de Kitava | Notas |
| - | --- | --- | --- | --- | --- | --- |
| 1 | Embate rodante: primer embate 90→75%, segundo embate 180→150% base; tiempo de ataque +1.0s (era +1.5s — cada slam resuelve 0.5s más rápido) | Cambios de habilidades | **+ S** | **+ S** | **+ S** | Según testing de la comunidad (ver `community-notes.md`): la cadencia 0.5s más rápida compensa de sobra el −17% de daño. DPS efectivo ≈ plano, con QoL claramente mejor. Reclasificado desde − L. |
| 2 | Terremoto: réplica 160→184% hasta 580→666% en gem 1–20 | Cambios de habilidades | **+ M** | **+ S** | **+ S** | Gran buff para Titán (Rompesuelos + Potenciación ancestral + Divisor de montañas escalan todas las réplicas). Menor para Adalid de guerra/Herrero. |
| 3 | Triturahuesos: calidad 30% → 20% velocidad de ataque incrementada | Cambios de habilidades | **− S** | **− S** | ~ | Nerf de QoL chico; la calidad aporta unos pocos %. |
| 4 | Tótem de guerrero ancestral: delay explícito del 50% del tiempo de ataque (era 0,6s oculto) | Cambios de habilidades | ~ | **+ M** | **+ M** | El delay ahora escala con la velocidad de ataque del arma — buff neto para builds de tótem con arma rápida (el playstyle de tótem de Adalid de guerra/Herrero). |
| 5 | Grito fortalecedor: shockwave por segmento de muro de escudos limitada; no puede multi-hit | Cambios de habilidades | **− S** | **− M** | **− S** | Combo Muro de escudos + Grito fortalecedor nerfeado. Castiga al Adalid de guerra inclinado a Muro de escudos más que a nadie. |
| 6 | Muro de escudos / Escudo resonante / Magma Barrier: 5–7 físico añadido por 15 armadura en escudo (era 6–8) | Cambios de habilidades | **− S** | **− S** | **− S** | ~17% menos daño añadido. Afecta a cada Guerrero de escudo. |
| 7 | Supercharged Slam: cambio solo de descripción | Cambios de habilidades | ~ | ~ | ~ | Sin cambio mecánico. |
| 8 | Punto clave Vínculo Ancestral: colocar tótems ya no cuesta/usa cargas; reserva 75 de spirit; **duplica el límite de tótems en vez de remover el límite** | Árbol de pasivas | ~ | **+ L** | **+ L** | Rework mayor. Antes removía el límite por completo; ahora es finito (típicamente 2 → 4 tótems). Buff neto para builds no-tótem (ya no es un nodo trampa) y **rework** para Guerreros dedicados a tótem — el playstyle cambia. |
| 9 | Notable Cornado: ya no 40% físico; ahora 3% vida máxima + 20% leech (era 3% reduced life + 30% leech) | Árbol de pasivas | **+ S** | **+ S** | **+ S** | El 40% físico perdido es lo importante. Más tanque, pero el daño crudo baja si tu build pasaba por Cornado por el físico. |
| 10 | Notable Voraz: ya no 20% instant leech; ahora 15% velocidad de ataque mientras hace leech | Árbol de pasivas | **− M** | **− L** | **− M** | "Instant leech" era una palanca clave de supervivencia del Guerrero. Castiga especialmente al Adalid de guerra de bleed. |
| 11 | Notable Commanding Rage: 2% velocidad de ataque de esbirro por cada 5 de Rage (era 1% por Rage) | Árbol de pasivas | ~ | **− S** | **− S** | Leve nerf efectivo para Guerreros de rage-stacking + esbirros (escalado de Manifest Weapon de Herrero). |
| 12 | Banner small AoE: 12% (era 15%); Tactician banner small: 16% (era 20%) | Árbol de pasivas | ~ | **− S** | ~ | Builds de Guerrero de bandera (mayormente Adalid de guerra Defiance/War Banner) reciben un golpe chico. |
| 13 | Arma de Ataque a Dos Manos: +Nivel a todas las Habilidades de Cuerpo a Cuerpo T1 = +5 (era +7) | Cambios de objetos | **− L** | **− L** | **− L** | **Gran nerf indirecto** a cada Guerrero de maza de dos manos. Los rolls de +Nivel eran cómo las builds de slam escalaban — perder 2 niveles en el tier top es enorme. |
| 14 | Maza de una mano rango base 1,0m | Cambios de objetos | **+ S** | **+ S** | **+ S** | Buff marginal de QoL de clearing para Guerreros 1H+escudo. |
| 15 | Modificador Bonded en guantes: 25% warcry CDR (era 15%) | Cambios de objetos | **+ S** | **+ M** | **+ S** | El Adalid de guerra se apoya más fuerte en los gritos de guerra; upgrade sustancial de CDR. |
| 16 | Stone Runes en Armas Marciales: 20/30/40% acumulación de stun (era 20/25/30%) | Cambios de objetos | **+ S** | **+ S** | **+ S** | Los slammers enfocados en stun ganan notablemente más acumulación en T2/T3. |
| 17 | Modificador Bonded en guantes: 25% magnitud de sangrado reducida sobre ti (era 15%) | Cambios de objetos | **+ S** | **+ S** | **+ S** | QoL defensivo — los mapas con monstruos de sangrado son menos castigadores. |
| 18 | Maza única Chober Chaber: +2-3 Nivel de Todas las Habilidades de Esbirros | Cambios de objetos únicos | ~ | ~ | **+ M** | Manifest Weapon de Herrero + Esqueletos pueden escalar mejor con esto. |
| 19 | Anillo Prized Pain: removido "Hace Daño de Espinas a enemigos a los que aturdís con melee" | Cambios de objetos únicos | **− S** | **− S** | **− S** | La build nicho thorns/stun muere — impacto chico. |
| 20 | Armadura de cuerpo Soul Mantle: ya no −20–30% vida de tótem; ahora +75 Spirit | Cambios de objetos únicos | ~ | **+ M** | **+ M** | Quality-of-life sólido para Guerreros de tótem hambrientos de spirit. |
| 21 | Anillo Blistering Bond: el sangrado ahora se convierte a fuego y el fuego contribuye a la magnitud del sangrado | Cambios de objetos únicos | ~ | **+ M** | **+ S** | Abre un camino de build de Adalid de guerra de fire-bleed. |
| 22 | Cambio de jugador: el sangrado sobre uno mismo ya no se amplifica al moverse | Cambios de jugador | **+ S** | **+ S** | **+ S** | QoL puramente defensivo — no afecta a los sangrados que tú infliges. |
| 23 | Cambio de habilidad Eternal Rage: debe estar activa en ambos sets de armas | Cambios de habilidades | **− S** | **− M** | **− S** | Builds de rage del Adalid de guerra con tech de weapon-swap impactadas. |

### Puntaje agregado (suma ponderada: ±L=±1.0, ±M=±0.3, ±S=±0.1)

| Ascendencia | Buffs | Nerfs | Neto |
| --- | --- | --- | --- |
| **Titán** | +0.0L · +1.0M · +0.7S = **+1.46** | +0.0L · −0.3M · −0.4S = **−0.34** | **+1.12** (buff neto) |
| **Adalid de guerra** | +1.0L · +1.5M · +0.8S = **+2.37** | +0.0L · −2.0M · −0.6S = **−1.16** | **+1.21** (buff neto) |
| **Herrero de Kitava** | +1.0L · +0.9M · +0.9S = **+1.88** | +0.0L · −0.6M · −0.5S = **−0.73** | **+1.15** (buff neto) |

> Caveat: esta rúbrica todavía pesa fuerte el nerf de +Nivel a Habilidades de Cuerpo a Cuerpo en objetos — ese cambio castiga ampliamente a los tres builds de maza a dos manos. Embate rodante, originalmente contado como el gran nerf por el lado de habilidades, fue reclasificado a un pequeño **buff** de QoL (ver `community-notes.md`); la imagen de "ganadores" se refuerza, impulsada por el **rework de Vínculo Ancestral** (enorme para playstyles de tótem), los únicos de bleed/warcry, y ahora el Embate rodante más snappy.

---

## Top builds entrando a 0.5 (heredadas de la meta 0.4)

**Caveat: los datos de popularidad de poe2.ninja están actualmente inaccesibles** (client-rendered, sin browser MCP conectado). Las páginas de build de Mobalytics listadas para cada ascendencia abajo son pre-0.5; describen lo que funcionaba en 0.4 y es el punto de partida para builds de semana-1 en 0.5.

### Titán
- **Titán de Terremoto (slam-aftershock).** Escalado core: Rompesuelos (25% réplica de slam) + Potenciación ancestral (cada 2do slam ancestrally boosted) + Divisor de montañas (cada 3er slam = 3 réplicas). **Impacto 0.5: el buff de Terremoto (#2) es un buff directo a la habilidad core; pero el −2 de +Nivel en arma (#13) es un golpe sustancial al escalado por objetos.** Neto levemente positivo.
- **Titán de Hammer of the Gods / Triturahuesos (burst single-target).** Forma descomunal duplica el escalado de pasivas pequeñas. **Impacto 0.5: nerf de calidad de Triturahuesos (#3) es chico; Hammer of the Gods sin tocar.**
- **Titán de Muro de escudos.** Era popular en 0.4 como una build de "aprietas un botón y limpias". **Impacto 0.5: nerf al daño añadido de Muro de escudos (#6) + nerf a Grito fortalecedor (#5).** Nerf agregado leve.

### Adalid de guerra
- **Adalid de guerra de Bleed Slam (Embate rodante → Triturahuesos).** Usaba gritos de guerra para clear, instant leech para supervivencia. **Impacto 0.5: el Notable Voraz removiendo instant leech (#10) y la calidad de Triturahuesos (#3) son los golpes reales; Embate rodante (#1) es ahora un buff chico de QoL (cadencia más rápida, DPS ≈ plano — ver `community-notes.md`).** Neto: pérdida de capa defensiva más que pérdida de DPS; el CDR de grito de guerra (#15) y la conversión bleed-fuego (#21) abren nuevas variantes.
- **Adalid de guerra de Tótem (Tótem de guerrero ancestral + Muro de escudos).** **Impacto 0.5: el cambio de delay de AWT (#4) realmente ayuda, y el rework de Vínculo Ancestral (#8) duplica la cantidad de tótems para builds que querían tótems baratos en spirit.** Neto positivo.
- **Adalid de guerra de Warcry (Gritos de guerra infinitos).** Spamea fortifying/seismic/etc. para buffs y clear. **Impacto 0.5: el CDR de warcry en guantes Bonded (#15) es un + limpio.** Neto positivo.

### Herrero de Kitava
- **Herrero de Asalto giratorio.** El cambio de calidad de "más velocidad de ataque" → "velocidad de ataque incrementada" es un nerf chico (menos escalado multiplicativo).
- **Herrero de Mesa / Twisted Imperium conversión fuego→frío.** Usa Twisted Imperium para convertir el daño de fuego de maza a frío. **Impacto 0.5: sin tocar directamente; el sistema de runeforging Verisium significa que las armas únicas de starter pueden ser mejoradas — esta es la principal narrativa "el Herrero llegó a A-tier" de las tier lists de terceros.** Vale la pena verificar una vez que Mobalytics opine.
- **Herrero de Manifest Weapon (minion-warrior).** **Impacto 0.5: Chober Chaber +2-3 a todas las habilidades de esbirros (#18) es un camino directo de buff; la nueva gema de asistencia Minion Splash Strength (en Contenido Nuevo) permite que los esbirros melee cleaven.** Buff sólido overall.

---

## Veredicto neto — Guerrero (preliminar, esperando la lista 0.5 de Mobalytics y datos de ninja)

| Ascendencia | Tier 0.4 (Mobalytics) | Veredicto 0.5 (este análisis) | Dirección | Por qué |
| --- | --- | --- | --- | --- |
| **Titán** | A | A | plano | El buff de Terremoto cancela el nerf de +Nivel del objeto; los nodos core sin tocar; sigue siendo el Guerrero "por defecto". |
| **Adalid de guerra** | B | A | **buffeado** | El rework de Vínculo Ancestral es un buff de fuerza gratis para variantes de tótem; el buff de CDR-warcry en guantes apila; los únicos de bleed-fuego abren nuevas builds. Compensado en parte por el nerf de leech de Voraz. |
| **Herrero de Kitava** | C | B–A | **buffeado** | Ganador indirecto por reforging Verisium + Chober Chaber + Minion Splash; el playstyle mecánico (armour-break + manifest weapon) sin tocar. |

**Recomendación de league-start (solo Guerrero):**
- **El más seguro:** Titán (defaults probados, todos los notables característicos intactos, pero espera que la meta sea levemente más lenta que en 0.4 por el nerf de +Nivel en arma).
- **Pick sleeper:** variante Adalid de guerra de Tótem (el rework de Vínculo Ancestral es el mayor buff de Guerrero del parche, aunque nadie esté hablando de eso todavía).
- **Arriesgado/creativo:** Herrero de Kitava Mesa o Manifest-Weapon. Las tier lists de terceros están alcistas; necesita verificación con datos reales de ladder.

---

## Validación de metodología — qué funcionó y qué arreglar

### Funcionó bien
- **Parseo de patch notes.** Splittear el dump de 370k caracteres en 10 secciones por slicing con `python` produjo chunks limpios y legibles. Voy a reusar el mismo directorio `patch_notes_0_5_0_sections/` para la pasada completa.
- **Cross-reference de poe2db.tw.** Confirmé que cada notable nombrado (Rompesuelos, Forma descomunal, Vínculo Ancestral, Voraz, etc.) existe con el texto actual de 0.5. El cross-referencing de cambios de patch-note al texto del nodo real es confiable.
- **El formato matriz.** Un cambio por fila × columnas de ascendencia × dirección/magnitud me deja reusar la matriz a través de los 8 archivos de clase sin repensar cada cambio.

### Issues a resolver antes de la pasada completa
- **Sin acceso a poe2.ninja.** El gap más grande. Sin ella no puedo decir "% de Titanes corriendo Terremoto vs Hammer of the Gods" — solo "estas builds existían en 0.4". Necesito input del usuario sobre cómo manejarlo:
  - Opción A: el usuario conecta Chrome browser MCP, yo scrapeo.
  - Opción B: el usuario pega screenshots/CSV de los leaderboards clave de clase+habilidad.
  - Opción C: procedemos sin ella y nos apoyamos en mobalytics + comentario de creadores.
- **La tier list 0.5 de Mobalytics todavía no salió.** Su página existente sigue siendo "0.4 League Starter Tier List (Predictions)". Por ahora me apoyo en el artículo de aoeah.com de terceros como una señal débil — debería marcarlo claramente y refrescar cuando Mobalytics publique.
- **Varias líneas del parche que rankée como "L" o "M" merecen verificación de un jugador real.** Específicamente:
  - Nerf T1 +Nivel a dos manos (#13) — ¿esto afecta al arma típica de league-starter, o solo a los items god-tier crafteados? Si es solo lo último, bajar a M.
  - Rework de Vínculo Ancestral (#8) — necesita confirmación de que "75 spirit por tótem" + "límite duplicado" realmente neta como un buff para builds de tótem típicas.

### Pregunta abierta para el usuario
- Algunas builds de Guerrero se splittean entre dos ascendencias (ej. "leveleá como Adalid de guerra hasta 41 después respec a Titán"). ¿El archivo por clase debería llamar a esos como un camino distinto, o solo describir cada ascendencia aisladamente?

---

## Fuentes usadas en este PoC

- Patch notes oficiales: <https://www.pathofexile.com/forum/view-thread/3932540>
- poe2db.tw página de Titán (nodos pasivos): <https://poe2db.tw/us/Titan>
- poe2db.tw home (confirma las 23 ascendencias, incluyendo las nuevas de 0.5): <https://poe2db.tw/us/>
- Tier list Mobalytics (sigue siendo 0.4): <https://mobalytics.gg/poe-2/tier-list>
- Builds de Guerrero en Mobalytics: <https://mobalytics.gg/poe-2/warrior-builds>
- Mobalytics por ascendencia: <https://mobalytics.gg/poe-2/titan-builds>, <https://mobalytics.gg/poe-2/warbringer-builds>, <https://mobalytics.gg/poe-2/smith-of-kitava-builds>
- Tier list 0.5 aoeah.com (terceros, señal débil): <https://www.aoeah.com/news/4539--poe-2-05-tier-list--best-class--league-starter-builds-return-of-the-ancients>
- League starters 0.5 iggm.com: <https://www.iggm.com/news/poe-2-patch-0-5-0-league-starter-builds-top-meta-picks-for-return-of-the-ancients>
- poe2.ninja (CONFIRMADO INACCESIBLE sin browser MCP): <https://poe2.ninja/builds>