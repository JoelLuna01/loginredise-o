# MIA - Modulo de información.

Front-end estático.

Esta versión no usa React ni componentes de backend. Solo contiene:

- `index.html`
- `src/styles.css`
- `src/app.js`
- `src/img/` para colocar el logo real

## Cómo abrirlo sin instalar nada

Abre directamente el archivo:

```text
index.html
```

También puedes arrastrar `index.html` al navegador.

Nota: si el logo no aparece al abrirlo directo, usa un servidor local sencillo porque algunos navegadores restringen rutas locales.

## Cómo correrlo con servidor local simple

Si tienes Python instalado:

```bash
python -m http.server 8080
```

Después abre:

```text
http://localhost:8080
```

## Logo 

Crea la carpeta si no existe:

```text
src/img/
```

Coloca el logo con este nombre:

```text
src/img/logo.png
```

Si tu archivo tiene otro nombre o formato, cambia esta línea en `index.html`:

```html
src="./src/img/logo.png"
```

Por ejemplo:

```html
src="./src/img/logo.jpg"
```

Si el logo no carga, la pantalla muestra un logo vectorial de respaldo.

## Integración con backend

La lógica visual está en `src/app.js`.

Actualmente el reconocimiento facial está simulado con:

```js
setTimeout(() => {
  if (state === "waiting") {
    setState("detected");
  }
}, 4500);
```

El backend debe reemplazar esa simulación por el evento real de reconocimiento facial.

Estados disponibles:

| Estado | Uso |
| --- | --- |
| `waiting` | Esperando rostro frente a cámara |
| `detected` | Rostro identificado, muestra bienvenida y progreso |
| `success` | Acceso concedido, listo para redirigir |

Para cambiar el nombre del colaborador, edita en `index.html` el texto:

```html
Juan Pérez
```

## Build opcional

No es necesario hacer build para entregar este front-end. La entrega principal es la carpeta con `index.html`, `src/styles.css`, `src/app.js` y `src/img/`.

Si el equipo desea validar el proyecto con Vite, puede ejecutar:

```bash
npm install
npm run build
```

Vite puede mostrar una advertencia porque `src/app.js` está conectado como script clásico para que el archivo también pueda abrirse directamente en navegador. Para despliegue simple, usa los archivos fuente tal como están.

## Notas

- No hay usuario, contraseña ni teclado.
- Los únicos controles manuales son `Cambiar idioma` y `Solicitar ayuda`.
- La pantalla está diseñada para kiosco industrial, autoservicio y lectura a distancia.
