# Portal Cautivo para pfSense - Hotel PelaosSa

## Descripción

Este es un portal cautivo personalizado diseñado para pfSense para el sector hotelero que incluye todos los elementos requeridos:

- ✅ Logo corporativo del hotel (icono SVG personalizado)
- ✅ Nombre del hotel (Hotel PelaosSa)
- ✅ Mensaje de bienvenida hotelero personalizado
- ✅ Campos de login (usuario y contraseña)
- ✅ Imagen de fondo personalizada
- ✅ Diseño responsive y moderno con tema hotelero
- ✅ Términos y condiciones específicos para huéspedes
- ✅ Información de la red WiFi del hotel

## Características Incluidas

### Elementos Visuales

- **Logo:** Icono SVG de hotel con diseño elegante y moderno
- **Nombre del Hotel:** "Hotel PelaosSa" con tipografía elegante
- **Imagen de Fondo:** Utiliza `img/fo.jpg` con overlay semitransparente
- **Diseño Responsivo:** Se adapta a dispositivos móviles y tablets
- **Colores Temáticos:** Azul corporativo y dorado para elegancia hotelera

### Funcionalidades

- **Autenticación:** Formulario compatible con pfSense para huéspedes
- **Validación:** Verificación de campos en tiempo real
- **Términos y Condiciones:** Modal emergente con políticas hoteleras
- **Información de Red:** Detalles sobre el WiFi gratuito del hotel
- **Animaciones:** Transiciones suaves y efectos visuales profesionales

### Características Hoteleras

- **Mensaje de Bienvenida:** Orientado a huéspedes del hotel
- **Información WiFi:** Específica para servicios hoteleros
- **Términos Personalizados:** Políticas de uso para huéspedes
- **Soporte 24/7:** Información de contacto con recepción

### Seguridad

- **Variables pfSense:** Integradas ($PORTAL_ACTION$, $PORTAL_REDIRURL$, $PORTAL_ZONE$)
- **Validación:** Campos requeridos y verificación de entrada
- **Monitoreo:** Información sobre el registro de actividades para seguridad hotelera

## Instalación en pfSense

### Paso 1: Acceder a pfSense

1. Conecte a la interfaz web de pfSense
2. Vaya a **Services > Captive Portal**
3. Seleccione la zona donde desea aplicar el portal

### Paso 2: Configurar el Portal Cautivo

1. En la pestaña **Captive Portal**, habilite el portal
2. Configure los siguientes parámetros:
   - **Interface:** Seleccione la interfaz WiFi
   - **Maximum concurrent connections:** Según sus necesidades
   - **Idle timeout:** 480 minutos (8 horas)
   - **Hard timeout:** 480 minutos (8 horas)

### Paso 3: Subir Archivos del Hotel

1. Vaya a la pestaña **File Manager**
2. Suba los siguientes archivos:
   - `login.html` (página principal del portal hotelero)
   - `css/captive-portal.css` (estilos personalizados del hotel)
   - `img/fo.jpg` (imagen de fondo del hotel)
   - `img/hotel-icon.svg` (icono SVG del hotel)

### Paso 4: Configurar HTML Personalizado

1. En la pestaña **Captive Portal**, desplácese hasta **Portal page contents**
2. Pegue el contenido de `login.html` en el campo correspondiente
3. O seleccione "Use an uploaded file" y elija `login.html`

### Paso 5: Configurar Autenticación

1. En **Authentication**, configure:
   - **Authentication Method:** Local User Manager o RADIUS
   - **Local User Manager:** Si usa usuarios locales
   - **RADIUS:** Si tiene servidor RADIUS configurado

### Paso 6: Aplicar Configuración

1. Haga clic en **Save** para guardar los cambios
2. Aplique la configuración haciendo clic en **Apply Changes**

## Estructura de Archivos

```
Pelaosssa/
├── login.html              # Página principal del portal cautivo hotelero
├── css/
│   └── captive-portal.css  # Estilos personalizados del hotel
├── img/
│   ├── fo.jpg              # Imagen de fondo del hotel
│   └── hotel-icon.svg      # Icono SVG personalizado del hotel
└── README.md               # Este archivo
```

## Personalización para Otros Hoteles

### Cambiar el Nombre del Hotel

Edite `login.html` y modifique:

```html
<h1 class="business-name">Hotel PelaosSa</h1>
```

### Cambiar el Mensaje de Bienvenida

Modifique el contenido en:

```html
<p class="welcome-message">Su mensaje de bienvenida hotelero aquí...</p>
```

### Cambiar la Imagen de Fondo

1. Reemplace `img/fo.jpg` con su imagen
2. O modifique la referencia en `css/captive-portal.css`:

```css
background: url("../img/su-imagen.jpg");
```

### Cambiar el Icono del Hotel

1. Reemplace `img/hotel-icon.svg` con su icono personalizado
2. O modifique la referencia en `login.html`:
```html
<img src="img/su-icono.svg" alt="Su Hotel" style="width: 80px; height: 80px;" />
```

### Cambiar Colores del Tema Hotelero

Modifique las variables de gradiente en `css/captive-portal.css`:

```css
/* Ejemplo para colores corporativos del hotel */
background: linear-gradient(135deg, #su-color-1 0%, #su-color-2 100%);
```

### Personalizar Información de la Red

Edite en `login.html` la sección wifi-info:

```html
<strong>Red:</strong> NombreRed-SuHotel<br />
<strong>Velocidad:</strong> Su descripción de velocidad<br />
<strong>Disponibilidad:</strong> Sus términos de disponibilidad
```

## Variables de pfSense Utilizadas

- `$PORTAL_ACTION$` - URL de acción del formulario
- `$PORTAL_REDIRURL$` - URL de redirección después del login
- `$PORTAL_ZONE$` - Zona del portal cautivo

## Navegadores Compatibles

- ✅ Chrome 80+
- ✅ Firefox 75+
- ✅ Safari 13+
- ✅ Edge 80+
- ✅ Navegadores móviles (iOS/Android)

## Solución de Problemas

### El portal no aparece

1. Verifique que el portal cautivo esté habilitado
2. Confirme que la interfaz correcta esté seleccionada
3. Revise que los archivos estén subidos correctamente

### Problemas de estilo

1. Verifique que `captive-portal.css` esté en la carpeta `css/`
2. Confirme que la ruta de la imagen de fondo sea correcta
3. Limpie la caché del navegador

### Errores de autenticación

1. Verifique la configuración del método de autenticación
2. Revise los logs de pfSense en **Status > System Logs > Portal Auth**
3. Confirme que las credenciales sean correctas

## Soporte

Para soporte técnico o personalizaciones adicionales, consulte la documentación oficial de pfSense o contacte al administrador del sistema.

---

**Desarrollado para pfSense** | Portal Cautivo Personalizado | Versión 1.0
