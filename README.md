# verymuch-public-assets

Assets visuales públicos de Verymuch.ai para covers, banners y headers.

Se sirven por URL raw de GitHub, que es lo que consumen Notion (covers de página) y el Tracker de contenido.

## Qué hay aquí

| Fichero | Qué es |
|---|---|
| `fondo-notion.png` | **Cover canónico de Notion.** Es el que aplica `creador-lead-magnets` (regla §4.9) a toda página de LM. |
| `Fondos Notion.png` | **Alias de compatibilidad**, byte a byte igual que `fondo-notion.png`. Existe solo porque los ~60 LMs ya publicados apuntan a esta URL. No usar en nada nuevo, pero **sí hay que sustituirlo cada vez que se sustituya el canónico**. |
| `fondo-notion.svg` | **Legado, no es la fuente.** Ver abajo. |
| `gifs/` | GIFs de posts, subidos por `creador-gifs`. Nomenclatura `YYYY-MM-DD-slug.gif`. |

## La fuente del cover (corregido el 04-sep-2026)

La fuente es **`brand-book/piezas/cover-notion/cover.html`** en `verymuch-ai/verymuch-skills`.
Se re-exporta con el `render.py` de esa carpeta y el PNG resultante se sube aquí.

> **`fondo-notion.svg` NO es la fuente**, aunque este README lo declaró así hasta hoy.
> No puede serlo: está a 1584×396 y el PNG a 2376×594, otra proporción. Y su nota decía
> que llevaba el texto trazado para no depender de Archivo ni DM Serif Display, que son
> las tipografías de la **identidad retirada el 03-ago-2026**. Se queda como legado.

## Convenciones

- **Nombres en kebab-case, sin espacios.** Un espacio se convierte en `%20` en la URL raw y ensucia cada referencia. `Fondos Notion.png` es legado, no un ejemplo a seguir.
- **PNG para lo que consume Notion.** La fuente es HTML y vive en el repo de skills, no aquí: este repo guarda binarios publicados, no fuentes.

## Diseñar un cover de Notion

El hueco del cover mide **30% del alto de la ventana × el ancho completo**, así que su proporción la marca la forma de la pantalla de quien mira, no su resolución: ~5,1:1 en un portátil 16:10, ~5,9:1 en un escritorio 16:9, ~7,8:1 en un ultrawide. Notion escala la imagen al ancho y **recorta lo que sobra desde el centro**, arriba y abajo por igual.

De ahí las tres reglas que hacen que un cover no haya que reposicionar nunca:

1. **El lienzo va a 2376×594 (4:1).** Más alto que el hueco en cualquier pantalla, que es lo que garantiza que el recorte sea siempre vertical. Una imagen más plana se recorta **de lado** en las pantallas menos panorámicas.
2. **Centra el bloque de contenido en el lienzo.** Lo que está centrado es lo último en recortarse.
3. **Deja en los bordes lo prescindible.** Es lo primero que desaparece en pantallas panorámicas.

Lo que se ve de la imagen, medido simulando los tres recortes:

| Pantalla | Proporción del hueco | De la imagen se ve |
|---|---|---|
| Portátil 16:10 | ~5,1:1 | y 64 a 529 |
| Escritorio 16:9 | ~5,9:1 | y 96 a 498 |
| Ultrawide | ~7,8:1 | y 145 a 449 |

Así que **la banda que sobrevive siempre es y 145 a 449**. Este README decía 145 a 478 y
no sale: lo que pasa de 449 se corta en ultrawide.

En móvil el recorte es **horizontal**, no vertical, y es severo: se pierde en torno al 60% del ancho. Nada fino ni pegado a los laterales sobrevive ahí.

> **Aviso de deriva.** El fichero publicado hasta el 04-sep-2026 estaba a **2700×443**
> (6,09:1), o sea se había salido de lo que este mismo README razona, y en portátil se
> recortaba de lado. Si vuelve a aparecer un cover con otra medida, este es el motivo
> por el que no.
