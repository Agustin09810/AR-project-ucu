# 👨‍💻 Guía de Desarrollo - Búsqueda del Tesoro AR

Esta guía proporciona información técnica para desarrolladores que deseen entender, modificar o extender el proyecto.

## 🏗️ Arquitectura del Sistema

### Componentes Principales

```
┌─────────────────────────────────────────────────────────┐
│                    index.html                           │
│              (Landing Page / Menu)                      │
└────────────────────┬────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────┐
│                ar-experience.html                       │
│  ┌───────────────────────────────────────────────────┐ │
│  │  A-Frame Scene (AR.js integration)                │ │
│  │  ┌─────────────────────────────────────────────┐  │ │
│  │  │  Marker Detection System                    │  │ │
│  │  │  - Pattern Recognition                      │  │ │
│  │  │  - Event Listeners (markerFound/Lost)       │  │ │
│  │  └─────────────────────────────────────────────┘  │ │
│  │                                                     │ │
│  │  ┌─────────────────────────────────────────────┐  │ │
│  │  │  Game Logic (JavaScript)                    │  │ │
│  │  │  - State Management                         │  │ │
│  │  │  - Progress Tracking                        │  │ │
│  │  │  - LocalStorage Persistence                 │  │ │
│  │  └─────────────────────────────────────────────┘  │ │
│  │                                                     │ │
│  │  ┌─────────────────────────────────────────────┐  │ │
│  │  │  UI Components                              │  │ │
│  │  │  - HUD (Progress Bar)                       │  │ │
│  │  │  - Notifications                            │  │ │
│  │  │  - Modals                                   │  │ │
│  │  └─────────────────────────────────────────────┘  │ │
│  └───────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────┘
```

## 📦 Estructura de Datos

### Game State Object

```javascript
const gameState = {
    markersFound: new Set(),        // Set de IDs de marcadores encontrados
    totalMarkers: 4,                // Total de marcadores en el juego
    markerData: {                   // Configuración de cada marcador
        0: {
            name: String,           // Nombre del marcador
            icon: String,           // Emoji/icono representativo
            message: String,        // Mensaje principal
            clue: String           // Pista para el siguiente paso
        }
        // ... más marcadores
    }
};
```

### LocalStorage Schema

```javascript
// Key: 'treasureHuntProgress'
// Value: JSON string del array de IDs de marcadores encontrados
// Ejemplo: "[0, 1, 2]"
localStorage.setItem('treasureHuntProgress', JSON.stringify([0, 1, 2]));
```

## 🔧 Sistema de Detección de Marcadores

### Componente A-Frame Personalizado

```javascript
AFRAME.registerComponent('registerevents', {
    init: function () {
        const marker = this.el;
        const markerId = parseInt(marker.id.split('-')[1]);

        // Evento cuando el marcador es detectado
        marker.addEventListener('markerFound', function() {
            console.log('Marker found:', markerId);
            onMarkerFound(markerId);
        });

        // Evento cuando el marcador se pierde
        marker.addEventListener('markerLost', function() {
            console.log('Marker lost:', markerId);
            // Opcional: agregar lógica adicional
        });
    }
});
```

### Flujo de Detección

```
Usuario apunta cámara a marcador
            ↓
AR.js detecta el patrón del marcador
            ↓
Se dispara evento 'markerFound'
            ↓
Se ejecuta onMarkerFound(markerId)
            ↓
Se verifica si ya fue encontrado
            ↓
Si es nuevo → Actualizar estado, UI, y guardar progreso
            ↓
Mostrar notificación con información
            ↓
Si completó todos → Mostrar modal de victoria
```

## 🎨 Sistema de Animaciones A-Frame

### Propiedades Animables

A-Frame permite animar cualquier propiedad de una entidad:

```html
<!-- Rotación continua -->
<a-box animation="property: rotation; to: 0 360 0; loop: true; dur: 3000"></a-box>

<!-- Movimiento oscilante -->
<a-cylinder animation="property: position; to: 0 1 0; dir: alternate; loop: true; dur: 1000"></a-cylinder>

<!-- Escala pulsante -->
<a-sphere animation="property: scale; to: 1.2 1.2 1.2; dir: alternate; loop: true; dur: 500"></a-sphere>
```

### Múltiples Animaciones

Para múltiples animaciones simultáneas, usa atributos con sufijos:

```html
<a-box
    animation__rotate="property: rotation; to: 0 360 0; loop: true; dur: 3000"
    animation__scale="property: scale; to: 1.5 1.5 1.5; dir: alternate; loop: true; dur: 1000">
</a-box>
```

## 🔊 Sistema de Audio

### Implementación de Sonidos

```javascript
function playSound(type) {
    const sounds = {
        success: 'data:audio/wav;base64,...',
        victory: 'data:audio/wav;base64,...'
    };

    try {
        const audio = new Audio(sounds[type]);
        audio.volume = 0.3;
        audio.play().catch(e => console.log('Audio play failed:', e));
    } catch (e) {
        console.log('Audio creation failed:', e);
    }
}
```

### Agregar Archivos de Audio Personalizados

Reemplaza los data URIs con rutas a archivos:

```javascript
const sounds = {
    success: './sounds/success.mp3',
    victory: './sounds/victory.mp3',
    ambient: './sounds/ambient.mp3'
};
```

## 🎯 Agregar Nuevos Marcadores

### Paso 1: Generar Patrón del Marcador

1. Visita [AR.js Marker Training](https://ar-js-org.github.io/AR.js/three.js/examples/marker-training/examples/generator.html)
2. Sube una imagen única (idealmente con alto contraste)
3. Descarga el archivo `.patt`
4. Guárdalo en `markers/pattern-marker-N.patt`

### Paso 2: Agregar HTML del Marcador

```html
<a-marker type="pattern" url="markers/pattern-marker-4.patt" id="marker-4" registerevents>
    <!-- Tu contenido 3D -->
    <a-sphere position="0 0.5 0" radius="0.5" material="color: #00FF00;">
        <a-animation attribute="rotation"
                     to="360 360 0"
                     dur="5000"
                     repeat="indefinite">
        </a-animation>
    </a-sphere>

    <a-text value="NUEVO MARCADOR"
            position="-1 1.5 0"
            color="#FFFFFF"
            align="center"
            width="2">
    </a-text>
</a-marker>
```

### Paso 3: Actualizar JavaScript

```javascript
const gameState = {
    markersFound: new Set(),
    totalMarkers: 5,  // ← Incrementar el total
    markerData: {
        // ... marcadores existentes
        4: {
            name: "Tu Nuevo Marcador",
            icon: "🎯",
            message: "Mensaje descriptivo",
            clue: "Pista para continuar"
        }
    }
};
```

### Paso 4: Actualizar UI

```html
<div class="marker-status" id="status-4">
    <div class="marker-icon">🎯</div>
    <div class="marker-label">Nombre</div>
</div>
```

## 🛠️ Debugging y Testing

### Console Logs Útiles

```javascript
// Ver estado actual del juego
console.log('Game State:', gameState);
console.log('Markers Found:', [...gameState.markersFound]);

// Ver progreso guardado
console.log('Saved Progress:',
    JSON.parse(localStorage.getItem('treasureHuntProgress')));

// Ver eventos de marcadores
marker.addEventListener('markerFound', function() {
    console.log('Marker detected:', this.id);
    console.log('Marker position:', this.object3D.position);
});
```

### Testing en Desktop

Para testing sin marcadores físicos:

```javascript
// Simular detección de marcador
function simulateMarkerFound(markerId) {
    onMarkerFound(markerId);
}

// Usar desde la consola del navegador
simulateMarkerFound(0);
simulateMarkerFound(1);
```

### Resetear Progreso

```javascript
// Limpiar todo el progreso guardado
function resetProgress() {
    localStorage.removeItem('treasureHuntProgress');
    location.reload();
}
```

## 🎨 Personalización Avanzada

### Agregar Modelos 3D

#### 1. Preparar el modelo

Usa formatos soportados por A-Frame:
- GLTF (.gltf, .glb) - Recomendado
- OBJ (.obj + .mtl)
- Collada (.dae)

#### 2. Agregar al proyecto

```html
<a-assets>
    <a-asset-item id="treasure-model" src="models/treasure.gltf"></a-asset-item>
</a-assets>

<a-marker type="pattern" url="markers/pattern-marker-3.patt" id="marker-3" registerevents>
    <a-entity gltf-model="#treasure-model"
              position="0 0 0"
              scale="0.5 0.5 0.5"
              animation="property: rotation; to: 0 360 0; loop: true; dur: 5000">
    </a-entity>
</a-marker>
```

### Efectos de Partículas

Para efectos visuales avanzados:

```html
<!-- Partículas brillantes -->
<a-entity position="0 0.5 0">
    <a-sphere position="0.5 0 0" radius="0.05" material="color: #FFEB3B; opacity: 0.7"
              animation="property: position; to: 0.5 1 0; dir: alternate; loop: true; dur: 1500">
    </a-sphere>
    <a-sphere position="-0.5 0 0" radius="0.05" material="color: #FFC107; opacity: 0.7"
              animation="property: position; to: -0.5 1 0; dir: alternate; loop: true; dur: 1500; delay: 300">
    </a-sphere>
</a-entity>
```

## 📱 Optimización para Móviles

### Performance Tips

```html
<!-- Renderer optimizations -->
<a-scene
    embedded
    arjs="sourceType: webcam;
          debugUIEnabled: false;
          detectionMode: mono_and_matrix;
          matrixCodeType: 3x3;
          maxDetectionRate: 30;
          canvasWidth: 640;
          canvasHeight: 480;"
    vr-mode-ui="enabled: false"
    renderer="logarithmicDepthBuffer: true;
              precision: medium;
              antialias: false;">
</a-scene>
```

### Reducir Complejidad de Geometría

```javascript
// Malo: Muchos polígonos
<a-sphere radius="1" segments-width="64" segments-height="64"></a-sphere>

// Bueno: Menos polígonos
<a-sphere radius="1" segments-width="16" segments-height="12"></a-sphere>
```

## 🔐 Seguridad y Permisos

### Manejo de Permisos de Cámara

```javascript
// Verificar soporte de getUserMedia
if (navigator.mediaDevices && navigator.mediaDevices.getUserMedia) {
    console.log('Camera API supported');
} else {
    console.error('Camera API not supported');
    alert('Tu navegador no soporta acceso a cámara');
}

// Manejar errores de permisos
navigator.mediaDevices.getUserMedia({ video: true })
    .then(stream => {
        console.log('Camera access granted');
    })
    .catch(error => {
        console.error('Camera access denied:', error);
        // Mostrar mensaje al usuario
    });
```

### HTTPS Requirement

Para producción, AR.js requiere HTTPS. Opciones de hosting:

1. **GitHub Pages** (HTTPS automático)
2. **Netlify** (HTTPS gratuito)
3. **Vercel** (HTTPS automático)
4. **Firebase Hosting** (HTTPS incluido)

## 📊 Analytics y Tracking

### Agregar Google Analytics

```html
<!-- En el <head> -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
    window.dataLayer = window.dataLayer || [];
    function gtag(){dataLayer.push(arguments);}
    gtag('js', new Date());
    gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

### Trackear Eventos Personalizados

```javascript
function onMarkerFound(markerId) {
    // ... lógica existente ...

    // Track evento
    if (typeof gtag !== 'undefined') {
        gtag('event', 'marker_found', {
            'event_category': 'AR_Game',
            'event_label': `Marker_${markerId}`,
            'value': markerId
        });
    }
}
```

## 🧪 Testing Checklist

### Pre-Deployment Testing

- [ ] Todos los marcadores se detectan correctamente
- [ ] Las animaciones funcionan suavemente
- [ ] El progreso se guarda correctamente
- [ ] La notificación aparece al encontrar marcadores
- [ ] El modal final se muestra al completar todos
- [ ] Funciona en Chrome móvil
- [ ] Funciona en Safari iOS
- [ ] Funciona en Firefox móvil
- [ ] La cámara se activa correctamente
- [ ] Los permisos se manejan adecuadamente
- [ ] El diseño es responsive
- [ ] Los marcadores impresos funcionan bien

### Cross-Browser Testing

```javascript
// Detectar navegador
const userAgent = navigator.userAgent;
const isSafari = /Safari/.test(userAgent) && !/Chrome/.test(userAgent);
const isChrome = /Chrome/.test(userAgent);
const isFirefox = /Firefox/.test(userAgent);

console.log('Browser:', {isSafari, isChrome, isFirefox});
```

## 🚀 Deployment

### GitHub Pages

```bash
# 1. Inicializar repositorio
git init
git add .
git commit -m "Initial commit: AR Treasure Hunt"

# 2. Crear repositorio en GitHub

# 3. Subir código
git remote add origin https://github.com/usuario/repo.git
git branch -M main
git push -u origin main

# 4. Habilitar GitHub Pages
# Settings → Pages → Source: main branch
```

### Vercel

```bash
# Instalar Vercel CLI
npm i -g vercel

# Desplegar
vercel

# Desplegar a producción
vercel --prod
```

## 📚 Recursos Adicionales

### Documentación Oficial

- [AR.js Docs](https://ar-js-org.github.io/AR.js-Docs/)
- [A-Frame Docs](https://aframe.io/docs/)
- [WebXR Device API](https://immersive-web.github.io/webxr/)

### Herramientas Útiles

- [AR.js Marker Generator](https://ar-js-org.github.io/AR.js/three.js/examples/marker-training/examples/generator.html)
- [A-Frame Inspector](https://aframe.io/docs/1.4.0/introduction/visual-inspector-and-dev-tools.html)
- [Sketchfab](https://sketchfab.com/) - Modelos 3D gratuitos

### Comunidad

- [AR.js GitHub](https://github.com/AR-js-org/AR.js)
- [A-Frame Slack](https://aframe.io/community/)
- [Stack Overflow - AR.js Tag](https://stackoverflow.com/questions/tagged/ar.js)

---

¿Necesitas ayuda? Abre un issue en el repositorio del proyecto.
