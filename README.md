# 📋 Checklist Técnicos 

Aplicación móvil para Android que permite a los técnicos de campo completar un checklist antes de visitar a un cliente, con envío automático de email y registro de información.

## ✨ Características

### Funcionalidades Principales
- ✅ **Checklist Interactivo**: 8 items predefinidos que los técnicos deben verificar antes de cada visita
- 📱 **Diseño Mobile-First**: Optimizado para dispositivos Android
- 💾 **Almacenamiento Local**: Los registros se guardan automáticamente en el dispositivo
- 📧 **Envío de Email**: Genera y envía un reporte profesional por email
- 📊 **Barra de Progreso**: Muestra visualmente el porcentaje de completitud
- 📝 **Historial de Checklists**: Acceso a todos los checklists completados previamente
- 🔄 **Modo Offline**: Funciona sin conexión a internet
- 📲 **Instalable como App**: Se instala como aplicación nativa en Android

### Información Capturada
- 👤 **Nombre del Técnico**
- 🎫 **Tickets a resolver** (múltiples)
- 📅 **Fecha y Hora** (captura automática)
- ✅ **Estado de cada item del checklist**
- 📊 **Porcentaje de completitud**

### Items del Checklist
1. Herramientas necesarias verificadas
2. Equipos de protección personal (EPP)
3. Documentación del cliente revisada
4. Repuestos/materiales necesarios
5. Ruta y ubicación del cliente confirmada
6. Contacto del cliente verificado
7. Backup de datos realizado (si aplica)
8. Credenciales de acceso disponibles

## 🚀 Instalación en Android

### Opción 1: Instalación como PWA (Recomendada)

1. **Abrir en Chrome/Edge**
   - Abre el archivo `index.html` en Chrome o Edge en tu dispositivo Android
   - O sube la aplicación a un servidor web y accede desde el navegador

2. **Instalar la App**
   - Toca el botón "📲 Instalar App" que aparece en la parte inferior
   - O en el menú del navegador, selecciona "Agregar a pantalla de inicio"
   - Acepta la instalación

3. **Usar como App Nativa**
   - La app aparecerá en tu menú de aplicaciones
   - Se abre en pantalla completa sin la barra del navegador
   - Funciona offline una vez instalada

### Opción 2: Servidor Local para Testing

```bash
# Usando Python (si tienes Python instalado)
python -m http.server 8000

# Luego accede desde tu Android a:
http://[IP-DE-TU-PC]:8000
```

### Opción 3: Hosting Web

Sube todos los archivos a cualquier servicio de hosting:
- GitHub Pages
- Netlify
- Vercel
- Firebase Hosting
- Servidor web propio

## 📖 Uso de la Aplicación

### 1. Completar Información Básica

```
👤 Nombre del Técnico: Juan Pérez
🎫 Tickets: #12345, #12346, #12347
📧 Email Destino: supervisor@knight.com
```

### 2. Marcar Items del Checklist

- Toca cada checkbox para marcar como completado
- Los items completados se muestran en verde con una marca ✓
- La barra de progreso se actualiza automáticamente

### 3. Enviar Checklist

- Presiona el botón "📧 Enviar Checklist"
- Se abrirá tu cliente de email predeterminado
- El email viene precargado con toda la información
- Envía el email normalmente

### 4. Ver Historial

- Toca "Ver Historial" para ver checklists anteriores
- Cada registro muestra:
  - Nombre del técnico
  - Fecha y hora
  - Tickets asociados
  - Porcentaje de completitud

## 📧 Formato del Email

El email generado incluye:

### Asunto
```
Checklist Pre-Visita - [Nombre Técnico] - Tickets: [Números]
```

### Contenido HTML
- 📊 **Resumen Ejecutivo**: Información clave en un cuadro destacado
- ✅ **Detalle del Checklist**: Tabla con todos los items y su estado
- ⚠️ **Alertas**: Si el checklist no está 100% completo
- 🎨 **Formato Profesional**: Diseño con colores corporativos

## 💾 Almacenamiento de Datos

### LocalStorage
- Los datos se guardan automáticamente en el navegador
- Permanecen incluso si cierras la app
- No se comparten con otros dispositivos
- Puedes borrar el historial limpiando los datos de la app

### Privacidad
- Todos los datos permanecen en el dispositivo
- No se envían a ningún servidor externo
- El email se genera localmente

## 🛠️ Estructura de Archivos

```
checklist-tecnicos/
│
├── index.html              # Aplicación principal (HTML + React)
├── manifest.json           # Configuración PWA
├── service-worker.js       # Service Worker para modo offline
├── icon-192.png           # Icono 192x192
├── icon-512.png           # Icono 512x512
└── README.md              # Esta documentación
```

## 🎨 Personalización

### Modificar Items del Checklist

En el archivo `index.html`, busca el array `checklistItems`:

```javascript
const [checklistItems, setChecklistItems] = useState([
  { id: 1, texto: 'Tu item personalizado', completado: false },
  // Agrega más items aquí
]);
```

### Cambiar Colores

Los colores principales están definidos en:
- **Primario**: `#667eea` (morado)
- **Secundario**: `#764ba2` (morado oscuro)
- **Éxito**: `#4CAF50` (verde)
- **Error**: `#f44336` (rojo)

### Modificar Email Destino Predeterminado

Cambia el placeholder en el campo de email:

```html
placeholder="tu-email@dominio.com"
```

## 🔧 Solución de Problemas

### La app no se instala
- Asegúrate de usar Chrome o Edge
- Verifica que estés en HTTPS o localhost
- Intenta desde el menú: "Agregar a pantalla de inicio"

### El email no se abre
- Verifica que tengas un cliente de email configurado
- Prueba con diferentes navegadores
- Los datos se guardan de todas formas en el historial

### Los datos no se guardan
- Verifica que el almacenamiento del navegador esté habilitado
- No uses modo incógnito
- Verifica los permisos de la app

### La app no funciona offline
- Asegúrate de haber abierto la app al menos una vez con internet
- Verifica que el Service Worker esté registrado
- Revisa la consola del navegador para errores

## 📱 Requisitos Técnicos

### Navegador
- Chrome 80+ (recomendado)
- Edge 80+
- Firefox 75+
- Samsung Internet 12+

### Sistema Operativo
- Android 5.0+ (Lollipop o superior)
- iOS 11.3+ (funciona pero con limitaciones de PWA)

### Permisos Requeridos
- Almacenamiento local (concedido automáticamente)
- Ningún otro permiso necesario

## 🔒 Seguridad

- No se almacenan contraseñas
- No hay transmisión de datos a servidores externos
- Los emails se envían a través de tu cliente configurado
- Todos los datos permanecen en tu dispositivo

## 📞 Soporte

Para soporte técnico o sugerencias:
- IT Service Management - Knight Therapeutics
- Email: [tu-email-soporte]

## 📝 Notas Importantes

1. **Respaldo de Datos**: Aunque los datos se guardan localmente, considera hacer respaldos periódicos exportando el historial
2. **Actualizaciones**: Para actualizar la app, simplemente recarga la página cuando haya una nueva versión disponible
3. **Compatibilidad**: La app está optimizada para Android, pero funciona en cualquier navegador moderno
4. **Modo Offline**: Después de la primera carga, la app funciona completamente offline

## 🎯 Roadmap Futuro

Funcionalidades planeadas:
- [ ] Exportar historial a Excel/PDF
- [ ] Checklist personalizable por tipo de visita
- [ ] Firma digital del técnico
- [ ] Fotos adjuntas
- [ ] Sincronización con servidor central
- [ ] Dashboard de métricas
- [ ] Notificaciones push
- [ ] Modo oscuro

## 📄 Licencia

Esta aplicación fue desarrollada para uso interno de Knight Therapeutics.

---

**Versión**: 1.0.0  
**Fecha**: Noviembre 2025  
**Desarrollado para**: Knight Therapeutics - IT Service Management
