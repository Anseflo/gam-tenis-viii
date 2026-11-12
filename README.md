# ATP GAM · VIII Edición

Sitio estático para GitHub Pages. No necesita Node, instalaciones ni compilación.

## Archivos
- `index.html`: estructura de la página.
- `styles.css`: identidad visual arcilla + pelota amarilla.
- `app.js`: filtros, cálculos de posiciones y cuadros de copas.
- `data/jugadores.json`: nombres, serie, grupo y penalización (`0`, `-1`, `-2`, `-3`).
- `data/resultados.json`: partidos de grupos. `gamesA` y `gamesB` en `null` indican partido pendiente.
- `data/ranking.json`: ranking histórico oficial (inicialmente vacío).
- `data/copas.json`: marcadores de eliminación directa (inicialmente vacíos).
- `data/bases.json`: 13 secciones pendientes del reglamento.
- `images/gam-tenis-logo.png`: **debes añadir tu logo original**; no se incluyó porque no estaba adjunto.

## Publicar en el repositorio ya creado
1. Descarga y descomprime el ZIP.
2. Abre `https://github.com/Anseflo/gam-tenis-viii`.
3. `Add file` → `Upload files` y sube **los archivos y carpetas dentro del ZIP**, conservando la estructura. Reemplaza `index.html` y `README.md` anteriores si GitHub lo solicita. El `data.js` antiguo ya no se usa: puedes borrarlo.
4. `Commit changes`.
5. En `Settings` → `Pages`, selecciona `Deploy from a branch`, `main`, `/(root)`. Ya estaba configurado en la conversación anterior.
6. Espera a que termine la publicación y abre `https://anseflo.github.io/gam-tenis-viii/`.

## Cómo editar datos
En GitHub abre el archivo JSON deseado, pulsa el lápiz (Edit), cambia los valores sin romper las comillas ni las comas y confirma con `Commit changes`. GitHub Pages republicará el sitio. No edites HTML para modificar resultados.

### Penalizaciones
En `jugadores.json` cambia `"penalizacion": 0` por `-1`, `-2` o `-3` según la sanción. El puntaje se calcula: `2 × partidos ganados + penalizacion`.

### Resultados
Ejemplo: `"gamesA": 6, "gamesB": 4`. Para pendientes usa `null` en ambos. No uses comillas para los números. Los cuadros de copas se completan por separado en `copas.json`.

### Copas
Ejemplo de entrada en `copas.json` dentro de `A` → `oro`: `"0": {"0": {"jugadores": ["Jugador 1", "Jugador 2"], "marcador": [6, 4]}}`. Los índices de ronda son 0 cuartos, 1 semifinales, 2 final. La final al mejor de tres sets puede expresarse temporalmente como sets ganados en `marcador`; el soporte de parciales completos puede añadirse cuando se disponga de resultados.

### Ranking
Agrega objetos como `{"posicion":1,"nombre":"Nombre","puntos":120,"ediciones":7}`. No se inventaron valores históricos.

### Bases
Reemplaza los textos pendientes en los 13 objetos de `bases.json` por el texto oficial.

## Notas
- Los cuatro archivos de origen indicaban 3 puntos por victoria; esta versión aplica **2 puntos por victoria** como establece la regla nueva.
- Los datos de origen son una instantánea; **no hay sincronización automática con Google Sheets**. Puedes editar los JSON directamente en GitHub.
- Nunca publiques las hojas privadas `Gastos del campeonato` ni `Participantes`.
- Para previsualizar localmente, usa un servidor HTTP local; abrir `index.html` con doble clic puede bloquear la lectura de JSON por seguridad del navegador.
