# CronoWork

Temporizador de intervalos para el gimnasio. Funciona como web app instalable en iPhone (PWA): sin App Store, sin Mac y sin cuenta de desarrollador.

## Qué hace

- **Ejercicio / Descanso / Series**: defines los segundos de trabajo, los segundos de descanso y cuántas veces se repite el ciclo.
- **Cuenta atrás de 5 s** antes de empezar, con un pitido por segundo.
- **Sonidos distintos** para cada fase:
  - Empieza una serie: dos tonos ascendentes (agudo y largo).
  - Empieza el descanso: dos tonos descendentes (graves).
  - Final de todas las series: fanfarria.
  - Opcional: pitidos 3-2-1 en los últimos segundos de cada fase.
- **Pausa, saltar fase y salir** (salir pide un segundo toque para evitar cortes accidentales).
- **Rutinas guardadas**: guarda la configuración actual con un nombre y cárgala con un toque. Incluye 3 ejemplos (Tabata, HIIT 40/20, Fuerza).
- Mantiene la pantalla encendida mientras corre el temporizador (Wake Lock) y funciona sin conexión una vez instalada.

## Instalar en el iPhone

1. Publica el repo con GitHub Pages: *Settings → Pages → Build and deployment → Deploy from a branch → `main` / `(root)`*.
2. Abre `https://<tu-usuario>.github.io/CronoWork/` en **Safari**.
3. Botón Compartir → **Añadir a pantalla de inicio**.

Se abre a pantalla completa, con su icono, como una app nativa.

## Limitaciones conocidas (iOS)

- Si bloqueas el iPhone o cambias de app, iOS congela la web app y los sonidos se detienen. Al volver, el tiempo se recalcula correctamente. Deja la app en primer plano durante el entrenamiento (la pantalla no se apaga sola).
- En iOS 17+ el sonido suena aunque el interruptor de silencio esté activado. En versiones anteriores, desactiva el modo silencio.
- Las rutinas se guardan en el propio dispositivo (no se sincronizan entre dispositivos).

## Estructura

| Archivo | Uso |
| --- | --- |
| `index.html` | App completa (HTML, CSS y JS sin dependencias) |
| `manifest.webmanifest` | Metadatos para instalarla como app |
| `sw.js` | Service worker para uso sin conexión |
| `*.png` | Iconos |
