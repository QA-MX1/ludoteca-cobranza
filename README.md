# Ludoteca de Cobranza · Crédito 365

Tablero de consulta rápida para collectors durante llamadas con clientes en mora. Reúne objeciones por arquetipo, terceros, extensiones, consecuencias del no pago, enfoque firme, cierre y guías de sí decir / no decir, con buscador en tiempo real y botón para copiar cada script.

Uso interno.

## Cómo usarla

- **Abrir:** entra al link de GitHub Pages del repositorio o abre `index.html` con doble clic en Chrome o Edge. No requiere instalación ni internet.
- **Buscar:** escribe lo que dice el cliente («no tengo dinero», «ya pagué», «no soy yo»). El buscador ignora acentos y mayúsculas, tolera errores leves y entiende lenguaje coloquial.
- **Atajos de teclado:** `/` o `Ctrl + K` para ir al buscador; flechas ↑ ↓ para recorrer resultados; `Enter` para abrir; `Esc` para borrar.
- **Copiar:** cada script tiene su botón «Copiar». Los datos entre corchetes, como `[nombre]` o `[fecha]`, se completan con la información del cliente.
- **Modo claro / oscuro:** botón en la esquina superior derecha.
- **Artículos del Código de Comercio (Art. 78, 83 y 389):** solo los usan los collectors G3. Aparecen marcados como «Solo G3».

## Estructura del repositorio

| Archivo | Contenido |
| --- | --- |
| `index.html` | La aplicación completa: contenido, estilos y código en un solo archivo. |
| `README.md` | Este documento. |

## Cómo editar el contenido

Todo el contenido está en `index.html`, dentro del objeto `const LUDOTECA = { ... }`, al inicio del bloque `<script>`. Arriba de ese objeto hay un comentario con la descripción de cada campo.

**Para editar un texto:** busca la frase y cámbiala dentro de sus comillas.

**Para agregar un escenario:**

1. Copia un escenario completo de la misma categoría, desde `{` hasta `},`.
2. Pégalo debajo y cambia el `id`: debe ser único y sin espacios (por ejemplo, `"no-tengo-trabajo-2"`).
3. Revisa que `categoria` sea una de estas: `apertura`, `terceros`, `objeciones`, `extensiones`, `consecuencias`, `firme`, `cierre` o `guias`.
4. Ajusta los textos: `situacion`, `clienteDice`, `respuesta`, `alternativas`, `firme`, `noDecir` y `cierre`.
5. En `etiquetas`, escribe frases como las dice el cliente («ando corto», «no traigo»). Es lo que más mejora el buscador.

**Reglas para no romper el archivo:**

- Las comillas rectas `"` solo abren y cierran cada texto. Dentro de un texto usa “ ” o « ».
- Pon una coma entre escenarios y ninguna después del último.
- Escribe los datos variables entre corchetes: `[nombre]`, `[fecha]`, `[hora]`, `[costo extensión]`.
- `"firme": null` oculta la variante firme de ese escenario.
- Los scripts que citan artículos van en el campo `"soloG3"`.

Guarda, recarga la página y prueba el buscador. Si la página queda en blanco, casi siempre falta una coma o una comilla.

## Cómo publicar una actualización

1. En GitHub, abre `index.html` y edítalo con el lápiz, o súbelo de nuevo con **Add file → Upload files** usando el mismo nombre.
2. Escribe una descripción corta del cambio y da clic en **Commit changes**.
3. GitHub Pages publica la nueva versión en unos minutos. Si no ves el cambio, recarga con `Ctrl + F5`.
