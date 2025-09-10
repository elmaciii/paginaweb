# 📰 Sistema de Noticias en Vivo & Radio

Una aplicación web moderna con CMS integrado que combina noticias en tiempo real con un reproductor de radio en vivo, desarrollada con HTML5, CSS3 y JavaScript puro.

## ✨ Características

### 📰 Noticias en Vivo
- **Actualización automática** cada 60 segundos
- **API real** de GNews.io para noticias actuales
- **Datos locales** como respaldo (data.json)
- **Interfaz responsive** optimizada para móvil y desktop
- **Spinner de carga** durante las actualizaciones
- **Formato de fecha** en español y relativo

### 🎵 Reproductor de Radio
- **Stream en vivo** desde radio online
- **Controles intuitivos** (Play/Pause)
- **Estado visual** del reproductor
- **Manejo de errores** robusto

### 🎨 Diseño Moderno
- **UI/UX profesional** con paleta de colores moderna
- **Header con navegación** completa y menú responsive
- **Noticia destacada** con imagen grande y botón de play
- **Grid de noticias** en 2 columnas optimizado
- **Reproductor de radio fijo** en la esquina inferior derecha
- **Responsive design** optimizado para móvil y desktop
- **Paleta de colores**: Azul, Violeta, Naranja, Rojo
- **Tipografía Roboto** para mejor legibilidad
- **Logo personalizable** en formato PNG

### 🛠️ CMS Integrado
- **Sistema de gestión** completo para noticias
- **Agregar, editar y eliminar** noticias fácilmente
- **Categorización** por temas (Política, Deportes, etc.)
- **Estados de publicación** (Publicada/Borrador)
- **Estadísticas en tiempo real** del contenido
- **Sincronización automática** con el sitio principal
- **Noticias automáticas** como respaldo cuando no hay contenido

## 🚀 Cómo ejecutar el proyecto

### Opción 1: Servidor local simple
```bash
# Navegar a la carpeta del proyecto
cd "C:\Users\Maxi\Desktop\Nueva carpeta"

# Usar Python (si está instalado)
python -m http.server 8000

# O usar Node.js (si está instalado)
npx serve .

# O usar PHP (si está instalado)
php -S localhost:8000
```

### Opción 2: Abrir directamente
1. Abrir `index.html` directamente en tu navegador
2. **Nota**: Algunas funciones pueden no funcionar debido a restricciones CORS

### Opción 3: Servidor web
- Subir todos los archivos a cualquier servidor web
- Acceder a través de HTTP/HTTPS

## 📁 Estructura del proyecto

```
📁 Nueva carpeta/
├── 📄 index.html          # Página principal
├── 🎨 styles.css          # Estilos principales
├── ⚡ app.js             # Lógica JavaScript principal
├── 📊 data.json          # Datos simulados de noticias
├── 🖼️ logo.png           # Logo personalizable
├── 🛠️ admin.html         # Panel de administración
├── 🎨 admin-styles.css   # Estilos del panel admin
├── ⚡ admin.js           # Lógica del panel admin
├── 🧪 test.html          # Página de pruebas
└── 📖 README.md          # Esta documentación
```

## 🔧 Configuración

### Sistema de Noticias
La aplicación usa un sistema de prioridades:
1. **Noticias del CMS** (si hay contenido cargado)
2. **Datos locales** (`data.json`)
3. **Noticias automáticas** (hardcodeadas como respaldo)

### Panel de Administración
- **Acceso**: Enlace "Admin" en la navegación o `/admin.html`
- **Autenticación**: Sistema de login con credenciales
- **Funcionalidades**: Gestión completa de noticias, configuración, analytics
- **Seguridad**: Sesiones con expiración automática (8 horas)
- **Almacenamiento**: LocalStorage del navegador
- **Sincronización**: Automática con el sitio principal

### Radio en Vivo
```javascript
// URL del stream de radio
const RADIO_URL = 'https://stream-ssl.radiosenlinea.com.ar:18069/';
```

### Logo Personalizable
- **Archivo**: `logo.png`
- **Formato**: PNG recomendado
- **Tamaño**: 200x60px óptimo
- **Fallback**: Texto "NOTICIAS" si no se encuentra

## 🛠️ Personalización

### Cambiar la radio
Edita en `app.js`:
```javascript
const CONFIG = {
    RADIO_URL: 'TU_URL_DE_RADIO_AQUI',
    // ... resto de configuración
};
```

### Modificar el intervalo de actualización
```javascript
const CONFIG = {
    UPDATE_INTERVAL: 30000, // 30 segundos en lugar de 60
    // ... resto de configuración
};
```

### Personalizar colores
Edita en `styles.css`:
```css
:root {
    --primary-blue: #3b82f6;      /* Azul principal */
    --secondary-violet: #8b5cf6;  /* Violeta */
    --accent-orange: #f97316;     /* Naranja */
    --accent-red: #ef4444;        /* Rojo */
}
```

### Cambiar el logo
1. Reemplaza el archivo `logo.png`
2. O edita el HTML en `index.html`:
```html
<img src="tu-logo.png" alt="Logo">
```

## 📱 Compatibilidad

### Navegadores soportados
- ✅ Chrome 60+
- ✅ Firefox 55+
- ✅ Safari 12+
- ✅ Edge 79+

### Dispositivos
- ✅ Desktop (Windows, macOS, Linux)
- ✅ Tablet (iPad, Android)
- ✅ Móvil (iOS, Android)

## 🎯 Funcionalidades técnicas

### Noticias
- **Sistema de prioridades** (CMS > Local > Hardcoded)
- **LocalStorage** para persistencia
- **Async/Await** para manejo asíncrono
- **Error handling** robusto
- **Auto-refresh** con setInterval
- **Formato de fechas** dinámico

### CMS
- **CRUD completo** (Create, Read, Update, Delete)
- **Validación de formularios** en tiempo real
- **Estados de publicación** (Publicada/Borrador)
- **Categorización** automática
- **Sincronización** con sitio principal
- **Estadísticas** en tiempo real

### Radio
- **HTML5 Audio API**
- **Event listeners** para estados
- **Error handling** para streams
- **Preload optimization**
- **Controles visuales** modernos

### UI/UX
- **CSS Custom Properties** (variables)
- **Flexbox y CSS Grid**
- **Media queries** responsive
- **Smooth animations**
- **Loading states**
- **Paleta de colores** moderna

## 🔍 Solución de problemas

### Las noticias no cargan
1. **Verificar Admin**: Ir a `/admin.html` para cargar noticias
2. **Verificar conexión**: Comprobar internet
3. **Consola del navegador**: Revisar errores (F12)
4. **Datos de respaldo**: Se cargarán automáticamente

### El Panel de Administración no funciona
1. **Credenciales**: Usar admin/admin123 por defecto
2. **Permisos del navegador**: Permitir LocalStorage
3. **JavaScript habilitado**: Verificar configuración
4. **Sesión expirada**: Las sesiones duran 8 horas

### La radio no reproduce
1. **URL del stream**: Verificar que sea válida
2. **Permisos de audio**: Permitir reproducción
3. **CORS**: Usar servidor local si es necesario

### Problemas de diseño
1. **Logo no aparece**: Verificar que `logo.png` existe
2. **Colores incorrectos**: Verificar variables CSS
3. **Responsive**: Probar en diferentes tamaños

## 📈 Mejoras futuras

- [ ] **PWA** (Progressive Web App)
- [ ] **Notificaciones push** para noticias importantes
- [ ] **Múltiples emisoras** de radio
- [ ] **Filtros** por categoría de noticias
- [ ] **Búsqueda** de noticias
- [ ] **Modo offline** completo
- [ ] **Temas personalizables**
- [ ] **API REST** para el CMS
- [ ] **Autenticación** de usuarios
- [ ] **Editor WYSIWYG** para noticias
- [ ] **Gestión de imágenes** integrada
- [ ] **Analytics** de visitas

## 🤝 Contribuciones

¡Las contribuciones son bienvenidas! Para contribuir:

1. Fork el proyecto
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Ver el archivo `LICENSE` para más detalles.

## 👨‍💻 Autor

Desarrollado con ❤️ para demostrar las capacidades de HTML5, CSS3 y JavaScript puro.

---

## 🎉 ¡Sistema Completo Listo!

**Características implementadas:**
- ✅ **Diseño moderno** con paleta de colores azul, violeta, naranja, rojo
- ✅ **Panel de administración** con autenticación
- ✅ **Navegación centrada** y bien alineada
- ✅ **Radio en vivo** funcional
- ✅ **Sistema de respaldo** automático
- ✅ **Logo personalizable** en PNG
- ✅ **Responsive design** completo
- ✅ **Sin dependencias** externas problemáticas

**¡Disfruta de tu sistema de noticias y radio en vivo! 🎉**
