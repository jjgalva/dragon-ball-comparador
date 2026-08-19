# ⚡ Dragon Ball · Comparador de Poder

Página web de fans donde eliges dos personajes de Dragon Ball, sus transformaciones,
y descubres quién es más fuerte.

**🌐 Página publicada:** https://jjgalva.github.io/dragon-ball-comparador/

## Qué hace

- **25 personajes**: Goku, Vegeta, Gohan, Piccolo, Freezer, Androide 17,
  Androide 18, Cell, Cell Max, Majin Buu, Trunks del Futuro, Goten, Black Goku,
  Zamasu, Omega Shenron, Broly, Gotenks, Gogeta, Vegetto, Krilin, Mr. Satán,
  Beerus, Jiren, Whis y Zeno-sama.
- **79 formas seleccionables** con su imagen propia: cada tarjeta tiene un
  desplegable de transformaciones (por ejemplo, Goku va de Base a Ultra Instinto
  pasando por SSJ, SSJ2, SSJ3, SSJ4, Dios y Blue) y el avatar cambia al elegirla.
- **Comparador**: seleccionas dos personajes, pulsas **¡LUCHAR!** y un modal
  declara al ganador según su nivel de poder, con cuántas veces supera al rival
  y barras de poder animadas (escala logarítmica). El ganador brilla con un aura
  dorada. Hay mensajes distintos según lo reñido del combate, y empate si los
  poderes coinciden.
- Detalles con cariño: Mr. Satán con poder 5, la fusión fallida de Gotenks
  (gordo, poder 500) y Zeno-sama con poder 999.999.999.999 — puede borrar
  universos, no hay pelea. Los androides 17 y 18 tienen dos formas por época
  (saga de Cell y Torneo del Poder), porque su nivel cambia por completo.

## Cómo se usa

Es una página estática sin dependencias: abre `index.html` en cualquier
navegador y funciona (también sin internet — las imágenes son locales).

Para desarrollarla en tu computadora:

```bash
git clone https://github.com/jjgalva/dragon-ball-comparador.git
cd dragon-ball-comparador
# abre index.html en el navegador, o sirve la carpeta:
python3 -m http.server 8000   # → http://localhost:8000
```

## Estructura

```
├── index.html   # Toda la app: HTML + CSS + JS en un solo archivo
├── img/         # 76 imágenes WebP (~3 MB): una por personaje y transformación
├── README.md
└── .github/workflows/deploy-pages.yml   # Despliegue automático a GitHub Pages
```

Los datos viven en el array `CHARACTERS` dentro de `index.html`. Cada personaje
tiene `id`, `name`, `race`, `emoji` (respaldo si una imagen falla), `color`
(degradado del avatar) y una lista `forms` con `{ name, power, img }`.

**Añadir un personaje o transformación** = añadir su imagen a `img/` y una
entrada en ese array. Nada más.

## Niveles de poder

Escala relativa inventada para el juego, inspirada en el manga, el anime y las
guías oficiales (los "niveles de poder" canónicos dejaron de tener sentido tras
la saga de Freezer 😄). Se editan en el campo `power` de cada forma.

## Publicación

La página se publica automáticamente en GitHub Pages: el workflow
`.github/workflows/deploy-pages.yml` despliega el repositorio en cada push a
`main`. Solo requiere activar Pages una vez en
*Settings → Pages → Source: GitHub Actions*.

## Créditos de las imágenes

Arte oficial de los juegos *Dragon Ball Z Dokkan Battle* y *Dragon Ball
Legends* (© Bandai Namco / Akatsuki), obtenido de archivos de assets públicos y
procesado (recorte + WebP 400px) para uso en esta página de fans. El Ultra Ego
de Vegeta y el Black Freezer usan renders coloreados del manga de *Dragon Ball
Super* alojados en Dragon Ball Wiki, ya que esas formas aún no tienen arte de
juego equivalente.

Página de fans sin ánimo de lucro. Dragon Ball es obra de Akira Toriyama.
