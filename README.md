# Proyecto eCommerce de Ropa

## Descripción
Este proyecto es una maqueta web de una tienda de ropa hecha con **HTML, CSS y JavaScript básico (sin frameworks)**.  
La idea principal es simular el flujo de compra de una app móvil/web:

1. Ver productos en la página principal.
2. Entrar al detalle de un producto.
3. Ir al checkout para revisar y pagar el pedido.

El proyecto está pensado como práctica de maquetación, organización de archivos y navegación entre vistas.

## Objetivo del proyecto
- Practicar estructura de un proyecto frontend.
- Construir interfaces responsive con HTML + CSS.
- Reutilizar una sola vista de detalle para varios productos usando parámetros en la URL.
- Simular un checkout visual sin backend.

## Tecnologías usadas
- **HTML5**
- **CSS3**
- **JavaScript (vanilla)**
- **Google Fonts (Encode Sans)**

## Estructura del proyecto

```bash
app_de_ecommerce_de_ropa/
├── index.html
├── README.md
├── css/
│   ├── variables.css
│   ├── style.css
│   ├── detail.css
│   └── checkout.css
├── storage/
│   └── img/
│       ├── Profile_1.png
│       ├── vestidoamarillo.png
│       ├── bolsorojo.png
│       ├── chaquetanegra.png
│       └── chaquetadecuerovintaje.png
└── views/
    ├── detail.html
    └── checkout.html
```

## Funcionalidades principales

### 1) Página principal (`index.html`)
- Header con saludo e icono de notificaciones.
- Barra de búsqueda visual.
- Chips de categorías.
- Grid de 4 productos.
- Navegación inferior (Inicio, Favoritos, Carrito, Perfil).
- Enlaces al detalle con parámetro `product`:
  - `views/detail.html?product=vestido`
  - `views/detail.html?product=bolso`
  - `views/detail.html?product=chaqueta_negra`
  - `views/detail.html?product=cuero_vintage`

### 2) Detalle de producto (`views/detail.html`)
- Se reutiliza una sola vista para varios productos.
- Carga dinámica del contenido según query params de la URL.
- Cambia automáticamente:
  - Imagen
  - Título
  - Rating y reseñas
  - Vistas
  - Descripción
  - Lista de detalles
  - Colores
  - Precio
- Selector visual de talla y color.
- Botón **Comprar ahora** que lleva al checkout.

### 3) Checkout (`views/checkout.html`)
- Muestra resumen del pedido con productos e imágenes.
- Selector de cantidad visual (+ y -).
- Información de envío.
- Método de pago (radio buttons).
- Resumen de subtotal, envío, descuento y total.
- Botón de pago con modal de compra exitosa (sin backend).

## Lógica de JavaScript (detalle dinámico)
En `views/detail.html` existe un objeto `PRODUCT_DATA` que funciona como base de datos local de productos.  
La función `setProductData(product)` toma el parámetro de la URL y renderiza los datos en el HTML.

Si no llega un parámetro válido, por defecto carga el producto `vestido`.

## Diseño y estilos
- `css/variables.css`: colores, variables y tokens globales.
- `css/style.css`: estilos de la vista principal.
- `css/detail.css`: estilos de la vista de detalle.
- `css/checkout.css`: estilos de checkout y modal.

El diseño está optimizado para verse bien en móvil y escritorio con una estética tipo app de compras.

## Recursos y assets
Las imágenes se guardan localmente en `storage/img/`.  
Se usan rutas relativas para que cada vista cargue sus assets correctamente según su ubicación en carpetas.

## Cómo ejecutar el proyecto
Como es un proyecto estático, se puede abrir directamente:

1. Abrir `index.html` en el navegador.

Recomendación:
- Usar una extensión como **Live Server** en VS Code para recarga automática.

## Flujo de navegación
1. El usuario entra a `index.html`.
2. Selecciona un producto (va a `views/detail.html?product=...`).
3. Revisa detalles y da clic en **Comprar ahora**.
4. Llega a `views/checkout.html` y finaliza la compra visualmente.

## Estado actual del proyecto
- Proyecto funcional a nivel de interfaz.
- Navegación entre vistas configurada.
- Estructura simplificada a una sola vista de detalle reutilizable.
- No tiene backend ni persistencia real de carrito/pagos.

## Mejoras futuras (propuesta)
- Conectar con backend para productos reales.
- Agregar carrito dinámico con `localStorage` o API.
- Validaciones de formulario en checkout.
- Implementar autenticación de usuario.
- Mejorar accesibilidad (aria, focus states, teclado).
- Añadir pruebas básicas de UI.
