# CHICHA · Cocina peruana

Sitio web para **CHICHA**, un restaurante ficticio de cocina peruana en Juliaca, Puno. Permite ver la carta, reservar una mesa con calendario y croquis de dos pisos, elegir platos, simular el pago con Yape o efectivo, obtener un comprobante y consultar la reserva con un código.

Proyecto del curso **Introducción a la Ingeniería de Sistemas e Informática** · NRC `[NRC]` · Docente: `[Nombre del docente]`

🌐 **Sitio en línea:** [PEGAR AQUÍ EL ENLACE DE PHANTEON](https://)

📱 **Código QR:** [`assets/img/qr-chicha.png`](assets/img/qr-chicha.png)

---

## Qué incluye

| Página | Contenido |
|---|---|
| Inicio | Portada, filosofía con palabras en quechua, "Elige tu experiencia" y galería |
| Menú principal | Accesos a Carta, Reserva, Nosotros y Contacto |
| Carta | 4 platos con popup (historia, ingredientes, precio) y acordeón de bebidas |
| Reserva | Calendario, croquis de mesas, pedido, pago y comprobante en 5 pasos |
| Mi reserva | Búsqueda por código o por nombre y mesa |
| Nosotros | Historia, valores y galería |
| Contacto | Formulario, mapa y WhatsApp |
| Gracias | Pantalla final |

## Tecnologías

- **WordPress** + tema **Hello Elementor**
- **Elementor** y **Elementor Pro** (Theme Builder, popups, formularios, transiciones)
- **HTML, CSS y JavaScript** para los widgets de reserva
- **XAMPP** (desarrollo local) y **Phanteon** (hosting)
- **All-in-One WP Migration** para pasar el sitio de local a la nube
- **Git y GitHub** para el control de versiones

## Identidad visual

| Color | Código | Uso |
|---|---|---|
| Vino | `#6B0F3A` | Principal, botones y logo |
| Carbón | `#241016` | Texto y footer |
| Crema | `#F7F1EA` | Fondo |
| Piedra | `#E4DBD2` | Divisiones |
| Oro | `#B8935A` | Detalles finos |
| Verde / Rojo | `#5C7A4C` / `#A4524A` | Disponible / ocupado |

Tipografías: **Playfair Display** (títulos) y **Lato** (textos).

## Estructura del repositorio

```
chicha-web/
├── assets/img/   Logos, fotos y código QR
├── code/         CSS global, parches y widgets HTML
├── export/       Plantillas de Elementor (.json) y base de datos (.sql)
├── docs/         Presentación e informe técnico
└── README.md
```

### Archivos principales de `code/`

| Archivo | Para qué sirve |
|---|---|
| `chicha-global.css` | CSS global (Elementor → Ajustes del sitio → CSS personalizado) |
| `chicha-global-parche.css`, `chicha-global-parche2.css` | Correcciones; se pegan al final del CSS global |
| `chicha-reserva-widget.html` | Widget de Reserva (widget HTML de Elementor) |
| `chicha-mi-reserva-widget.html` | Widget de Mi reserva |
| `chicha-carta-agregar.html` | "Agregar al pedido" para la Carta y los popups |

## Cómo reproducir el proyecto

### Opción A: importar el sitio ya hecho

1. Instalar WordPress (local con XAMPP o en un hosting).
2. Instalar el plugin **All-in-One WP Migration**.
3. Ir a *All-in-One WP Migration → Importar* y cargar el archivo `.wpress` del sitio.
4. Guardar de nuevo *Ajustes → Enlaces permanentes*.
5. Si quedaron enlaces a `localhost`: *Elementor → Herramientas → Reemplazar URL* y *Regenerar CSS y datos*.
6. Activar la licencia de Elementor Pro.

### Opción B: construirlo desde cero

1. Iniciar Apache y MySQL en XAMPP. En `php.ini` usar `memory_limit = 512M`, `upload_max_filesize = 64M`, `post_max_size = 64M` y `max_execution_time = 300`.
2. Instalar WordPress, el tema **Hello Elementor** y los plugins **Elementor** y **Elementor Pro**.
3. Crear las páginas: Inicio, Menu, Carta, Reserva, Mi reserva, Nosotros, Contacto y Gracias, y poner Inicio como página de inicio.
4. En Elementor configurar colores y fuentes globales, y pegar `chicha-global.css` y los dos parches.
5. Crear el header y el footer con el Theme Builder (condición: todo el sitio).
6. Armar cada página y pegar los widgets HTML de `code/` en las páginas Reserva, Mi reserva y Carta.
7. Crear los 4 popups de los platos y enlazarlos desde la Carta.

El detalle completo está en el informe técnico en [`docs/`](docs/).

## Notas importantes

- Las reservas se guardan en el **navegador** de cada usuario (`localStorage`); no hay base de datos central, así que son de demostración. Los códigos `CHI-0314` (pagada) y `CHI-0420` (con deuda) son ejemplos fijos.
- La disponibilidad de días y mesas es simulada.
- El comprobante es una constancia de reserva y pago; no es boleta electrónica.
- Desde XAMPP los correos del formulario no se envían; en el hosting se necesita **WP Mail SMTP**.
- Las fotos son referenciales. `[Indicar fuente o autoría de las imágenes]`

## Equipo

| Integrante | Responsabilidad |
|---|---|
| `[Integrante 1]` | Ajustes globales, header, footer y animaciones |
| `[Integrante 2]` | Inicio, Carta, popups y Nosotros |
| `[Integrante 3]` | Reserva, Mi reserva y comprobante |
| `[Integrante 4]` | Contacto, hosting, GitHub, QR y presentación |

## Licencia

Proyecto académico sin fines comerciales. WordPress se distribuye bajo licencia GPL v2 o posterior. Elementor Pro requiere licencia propia.
