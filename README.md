# DIPPEA · Cookies Fries

Página web de **DIPPEA**, tienda de galletas en presentación de papitas fritas, acompañadas siempre de su dip. Basada en el kit de marca y el menú de la marca. Caracas, Venezuela.

> *Conecta tu vibe, dippea tu cookie.*

## Qué incluye

- **Portada** con el lema de la marca, la mascota Flow Steve y un botón "Arma tu pedido" que palpita.
- **Menú** en dos columnas: cookies a la izquierda y dips a la derecha. Cada bloque tiene foto, nombre y descripción.
  - Al pasar el cursor, el bloque se agranda y muestra "+ Agregar".
  - Al hacer clic, el producto se agrega automáticamente al pedido. Un aviso confirma la acción y lleva a la sección de armado.
- **Arma tu pedido**: dip (izquierda) y tamaño (derecha), más la elección de sabores.
  - 6 galletas + dip: $5
  - 10 galletas + dip: $7
  - Pedido personalizado: cuadro de texto libre, precio a convenir
  - Los paquetes surtidos (más de un sabor) tienen costo adicional
- **Envío por WhatsApp**: el pedido se arma como mensaje y se abre WhatsApp listo para enviar.
- **Contacto** en el pie de página: ubicación, correo, teléfonos y TikTok.

## Productos

| Cookies | Descripción |
|---|---|
| Dippea Chips | Galleta de vainilla con chispas de chocolate negro |
| Dippea Velvet | Galleta de Red Velvet con chispas de chocolate blanco |
| Dippea Flips | Galleta de vainilla con trozos y crema de Flips en su masa |

| Dips | Descripción |
|---|---|
| Augustus Gloop | Ovomaltina |
| Casper Cream | Queso crema dulce |
| Steve Cream | Arequipe |

## Estructura del proyecto

```
.
├── index.html   # Toda la página: HTML, CSS, JavaScript e imágenes incrustadas
└── README.md
```

Es un sitio **estático de un solo archivo**: no tiene dependencias, ni build, ni variables de entorno. Las imágenes van incrustadas en el HTML (base64), por eso pesa unos 250 KB. Las únicas cargas externas son las fuentes de Google Fonts (Fredoka y Roboto).

## Publicar en Vercel

1. Sube el repositorio a GitHub.
2. En [vercel.com](https://vercel.com), crea un proyecto nuevo e importa el repositorio.
3. Configuración:
   - **Root Directory:** `./` (o la carpeta donde esté `index.html`)
   - **Application Preset:** `Other`
   - **Build and Output Settings / Environment Variables:** dejar vacíos
4. Pulsa **Deploy**. Cada `git push` a `main` vuelve a publicar la página automáticamente.

Si Vercel muestra un 404, revisa que `index.html` esté en la raíz del repositorio (o en el Root Directory configurado) y que se llame exactamente `index.html`.

## Cómo editar

Todo está en `index.html`.

| Qué cambiar | Dónde buscar |
|---|---|
| Número de WhatsApp de pedidos | En el JavaScript: `const F=[...],WA="..."` (código de país, sin signos ni espacios) |
| Precios | Botones de tamaño (`id="size"`) y la línea `size==6?5:7` en el JavaScript |
| Nombres y descripciones de productos | Tarjetas `<div class="card" data-t="cookie">` y `data-t="dip"` |
| Costo de paquetes surtidos | Ahora muestra "+ extra"; se cambia en la función `draw()` |
| Contactos | Sección `<footer id="contacto">` |
| Colores | Variables CSS al inicio del `<style>` (`--red`, `--yellow`, `--brown`, `--cream`) |

Al agregar un producto nuevo, hay que añadir su tarjeta en el menú. Si es una cookie, también hay que sumarla a la lista `F` del JavaScript. Si es un dip, hay que añadirlo a los botones de `id="dip"`.

## Identidad de marca

**Colores**

| Color | Hex |
|---|---|
| Rojo | `#E3000E` |
| Amarillo | `#FFBF11` |
| Café | `#763F10` |
| Crema | `#FFEFD5` |

**Tipografías:** el kit de marca define Wedges (encabezados), Fredoka (subtítulos) y Roboto (texto). Wedges no está disponible en Google Fonts, así que la página usa Fredoka en los títulos. Si se consigue el archivo de la fuente, se puede agregar con `@font-face`.

**Mascota:** Flow Steve, "Dippea con flow".

## Contacto

- Ubicación: Caracas, Venezuela
- Correo: dippeacookies@gmail.com
- Teléfonos: +58 0414 9030058 · +58 0414 1282229
- TikTok: [@dippea_ve](https://www.tiktok.com/@dippea_ve)

## Pendientes

- Confirmar cuál de los dos números es el de WhatsApp para pedidos.
- Definir el costo adicional de los paquetes surtidos.
- Foto del dip Augustus Gloop en ovomaltina (ahora usa la foto del dip de chocolate).
- Foto completa de Dippea Chips (la actual viene cortada del kit de marca).
- Mascota en PNG con fondo transparente, para mejorar el recorte del brillo neón.
- Archivo de la fuente Wedges.
- Dominio propio.
- Definir métodos de pago y zonas de entrega o retiro en Caracas.

## Nota sobre Vercel

El plan Hobby de Vercel es solo para uso personal y no comercial. Cuando la página pase a ser el canal de venta del negocio, hay que pasar a un plan Pro.
