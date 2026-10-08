# Balón de gas

App personal para llevar el control de los balones de gas licuado: registra cuándo abres uno nuevo, cuenta los días de uso hasta que lo reemplazas y guarda el historial para calcular cuánto dura en promedio.

## Qué hace

- **Abrir nuevo balón**: indica la fecha de apertura (por defecto hoy). Si había uno en uso, se cierra en esa misma fecha.
- **Registrar compra**: guarda un balón comprado que aún no se abre (reserva). Al usar "Abrir balón de reserva", ese balón pasa a estar en uso y el actual se cierra en la misma fecha.
- **Dos balones de 45 kg**: la tarjeta principal dibuja el balón en uso, coloreado según lo que queda (estimado con tu promedio de días), y el de reserva, lleno si está comprado y sin abrir o vacío si no hay reserva.
- **Días de uso**: muestra cuántos días lleva el balón actual, el porcentaje consumido y la fecha estimada de cambio.
- **Historial**: lista de todos los balones con fechas, días de uso, tamaño y precio (opcionales). Cada registro se puede editar o eliminar.
- **Registros anteriores**: botón para ingresar a mano balones que ya usaste, con sus fechas de apertura y cierre.
- **Resumen**: promedio, balón más corto y más largo, gráfico de días por balón y gasto medio por día cuando hay precios.
- **Respaldo**: copia todos los registros como texto y restáuralos desde ahí (los datos viven solo en el dispositivo).

## Instalar en el iPhone

1. En GitHub, ve a **Settings → Pages** y publica la rama `main` desde la raíz (`/`). La app queda en `https://pablocarvallo.github.io/gas/`.
2. Abre esa dirección en **Safari** en el iPhone.
3. Toca **Compartir → Añadir a pantalla de inicio**.

Se abre como app independiente, con su icono, y funciona sin conexión.

## Archivos

| Archivo | Uso |
| --- | --- |
| `index.html` | La app completa (HTML, CSS y JavaScript sin dependencias de compilación) |
| `manifest.webmanifest` | Nombre, colores e iconos de la app instalada |
| `sw.js` | Service worker para uso sin conexión |
| `icons/icon-full.svg` | Icono original a pantalla completa (fuente de los PNG) |
| `icons/icon.svg` | Icono con esquinas redondeadas (favicon) |
| `icons/apple-touch-icon.png` | Icono de 180 px para la pantalla de inicio del iPhone |
| `icons/icon-192.png`, `icons/icon-512.png`, `icons/icon-1024.png` | Iconos del manifiesto y archivo de alta resolución |

## Datos

Los registros se guardan en `localStorage` del navegador bajo la clave `balon-gas-registros`. Cada registro tiene fecha de compra (opcional), fecha de apertura (vacía mientras es reserva), fecha de cierre (vacía mientras está en uso), tamaño en kg y precio en pesos.
