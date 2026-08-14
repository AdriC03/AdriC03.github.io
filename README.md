# Portfolio — Adrián Castillo

**En vivo: https://adric03.github.io**

Web personal de una sola página, sin dependencias externas ni build. Todo va en
`index.html`: estilos, animaciones y lógica.

```
portfolio-adrian/
├── index.html                       la web entera
└── assets/
    ├── adrian.jpg                   foto del hero
    └── CV_Adrian_Castillo.pdf       el CV que se descarga
```

## Verla en local

Doble clic en `index.html`. No hace falta nada más.

## Publicar cambios

Al hacer push a `main`, GitHub Pages republica la web sola en un par de minutos:

```bash
git add . && git commit -m "Actualiza el portfolio" && git push
```

## Qué puedes ajustar

Todo lo editable está en constantes al principio del `<script>`:

- `PROJECTS` — los cuatro proyectos, su año y el detalle que sale en la ventana
  modal. El año del sistema en C++ está puesto en 2023 a ojo; los otros tres son
  los que confirmaste (imágenes 2025, e-commerce 2026, agente RL 2026).
- `TIMELINE` — la trayectoria 2022 → 2026: fundamentos con C, POO y C++, bases de
  datos, datos/ML y el último curso con los dos proyectos grandes.
- `BARS` — los porcentajes de los lenguajes. Son una estimación; ajústalos a lo
  que consideres justo antes de una entrevista, porque te van a preguntar por ellos.
- `WHY`, `PITCH`, `LANGS`, `MARQUEE_A/B` — el resto de textos.
- `LINKEDIN`, `GITHUB`, `EMAIL` — los enlaces de contacto.

## Animaciones

- **Preloader** con contador y cortinas que se abren al terminar.
- **Cursor personalizado** (anillo con retardo + punto) que crece sobre lo pulsable.
  Se desactiva solo en móvil y táctil.
- **Hero**: nombre letra a letra, entrada escalonada del resto, máquina de escribir,
  foto con zoom lento (Ken Burns), halo que respira, anillos girando y badges con
  parallax al hacer scroll.
- **Fondo**: red de partículas en `<canvas>` que se aparta del ratón, orbes de color
  a la deriva y rejilla difuminada.
- **Al entrar en pantalla**: títulos revelados con `clip-path`, rótulos de sección
  con efecto *scramble*, contadores, barras de nivel con brillo, anillos de idiomas
  y entradas escalonadas de tarjetas, pills y líneas de contacto.
- **Trayectoria**: la línea del tiempo se dibuja según bajas y cada hito aparece.
- **Tarjetas**: inclinación 3D, foco que sigue al cursor y destello que las cruza.
- **Navegación**: barra de progreso, pastilla que se desliza a la sección activa,
  nav que se esconde al bajar y botón flotante con anillo de progreso.
- **Botones**: efecto magnético y onda al pulsar.
- **Formulario**: confeti al enviar.
- **Estela del cursor** (siete puntos con retardo creciente) y un foco de luz de
  fondo que sigue al ratón.
- **Navegador lateral de puntos** con el nombre de cada sección al pasar por encima.
- **Párrafos que entran palabra a palabra** al llegar a pantalla.
- **Borde de luz giratorio** alrededor de la tarjeta de proyecto que señalas.
- **El hero se desvanece y se aleja** al salir de pantalla (solo en escritorio).
- **Las marquesinas se inclinan** según la velocidad a la que haces scroll.
- **Inclinación 3D** también en las tarjetas de "por qué yo" y en las métricas.
- **Las pills del stack se apartan** del cursor como un campo magnético.
- Todo respeta `prefers-reduced-motion`: si el sistema lo pide, se desactiva.

## Detalles técnicos

- Sin librerías: HTML, CSS y JavaScript nativo. Un archivo, cero dependencias.
- `IntersectionObserver` para los reveals y un único handler de scroll con
  `requestAnimationFrame` para el resto.
- Filtro por perfil (Backend / Datos & ML / Videojuegos) que atenúa los proyectos
  que no encajan y cambia el argumento de venta.
- El formulario de contacto abre el cliente de correo con el mensaje ya redactado
  (`mailto:`), así que funciona sin backend. Los datos de contacto se copian al
  portapapeles con un clic.
