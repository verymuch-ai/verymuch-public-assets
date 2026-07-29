# verymuch-public-assets

Assets visuales públicos de Verymuch.ai para covers, banners y headers.

Se sirven por URL raw de GitHub, que es lo que consumen Notion (covers de página) y el Tracker de contenido.

## Qué hay aquí

| Fichero | Qué es |
|---|---|
| `fondo-notion.png` | **Cover canónico de Notion.** Es el que aplica `creador-lead-magnets` (regla §4.9) a toda página de LM. |
| `fondo-notion.svg` | Fuente editable del cover. Todo cambio de diseño se hace aquí y se re-exporta el PNG. |
| `Fondos Notion.png` | **Alias de compatibilidad**, byte a byte igual que `fondo-notion.png`. Existe solo porque los ~60 LMs ya publicados apuntan a esta URL. No usar en nada nuevo. |
| `gifs/` | GIFs de posts, subidos por `creador-gifs`. Nomenclatura `YYYY-MM-DD-slug.gif`. |

## Convenciones

- **Nombres en kebab-case, sin espacios.** Un espacio se convierte en `%20` en la URL raw y ensucia cada referencia. `Fondos Notion.png` es legado, no un ejemplo a seguir.
- **PNG para lo que consume Notion, SVG como fuente.** El SVG lleva el texto trazado a paths, así que no depende de que el renderizador tenga Archivo ni DM Serif Display instaladas.

## Diseñar un cover de Notion

El hueco del cover mide **30% del alto de la ventana × el ancho completo**, así que su proporción la marca la forma de la pantalla de quien mira, no su resolución: ~5,1:1 en un portátil 16:10, ~5,9:1 en un escritorio 16:9, ~7,8:1 en un ultrawide. Notion escala la imagen al ancho y **recorta lo que sobra desde el centro**, arriba y abajo por igual.

De ahí las dos reglas que hacen que un cover no haya que reposicionar nunca:

1. **Centra el bloque de contenido en el lienzo.** Lo que está centrado es lo último en recortarse.
2. **Deja en los bordes lo prescindible.** Es lo primero que desaparece en pantallas panorámicas.

En `fondo-notion.png` (2376×594) eso se traduce en: contenido entre `y 145` y `y 478`, con los badges de certificación pegados al borde inferior a propósito, para que sean lo primero que se sacrifique.

En móvil el recorte es **horizontal**, no vertical, y es severo: se pierde en torno al 60% del ancho. Nada fino ni pegado a los laterales sobrevive ahí.
