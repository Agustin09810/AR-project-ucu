# 🏛️ Búsqueda del Tesoro en Realidad Aumentada

Una experiencia de Realidad Aumentada (AR) interactiva que transforma el Edificio Sacré Coeur en un juego de búsqueda del tesoro utilizando AR.js y A-Frame.

## 📚 Guías Rápidas

**¿Eres organizador o jugador?** Tenemos guías específicas para ti:

- 🎯 **[Guía para Organizadores](GUIA_ORGANIZADORES.md)** - Todo lo que necesitas para organizar el evento
- 🎮 **[Guía para Jugadores](GUIA_JUGADORES.md)** - Instrucciones paso a paso para jugar
- 🚀 **[Inicio Rápido](QUICK_START.md)** - Empieza en 5 minutos
- 👨‍💻 **[Guía de Desarrollo](DEVELOPER_GUIDE.md)** - Para personalizar y extender
- 💡 **[Ejemplos de Código](EXAMPLES.md)** - Snippets y extensiones

## 🎯 Descripción del Proyecto

Este proyecto es una aplicación web de Realidad Aumentada que permite a los usuarios explorar el Edificio Sacré Coeur mediante la búsqueda de marcadores AR distribuidos por el edificio. Cada marcador revela una pista y muestra contenido 3D interactivo que guía a los jugadores hacia el "tesoro final" - el descubrimiento de que el verdadero tesoro del edificio es el conocimiento que se transmite en sus aulas.

## ✨ Características

- **4 Marcadores AR únicos** con contenido 3D diferente
- **Sistema de progreso** que guarda tu avance localmente
- **Notificaciones interactivas** cuando encuentras cada marcador
- **Animaciones 3D** en cada marcador (rotaciones, movimientos, efectos de brillo)
- **Historia narrativa** que se desarrolla al encontrar cada marcador
- **Interfaz responsive** optimizada para dispositivos móviles
- **Feedback sonoro** (efectos de sonido al encontrar marcadores)
- **Revelación final** cuando completas la búsqueda

## 🛠️ Tecnologías Utilizadas

- **[AR.js](https://ar-js-org.github.io/AR.js/)** - Biblioteca de Realidad Aumentada para la web
- **[A-Frame](https://aframe.io/)** - Framework para crear experiencias 3D/VR/AR
- **HTML5, CSS3, JavaScript** - Tecnologías web estándar
- **LocalStorage** - Para guardar el progreso del jugador

## 📁 Estructura del Proyecto

```
AR-project-ucu/
├── index.html              # Página de inicio con instrucciones
├── ar-experience.html      # Experiencia AR principal
├── markers-print.html      # Página para imprimir marcadores
├── markers/                # Archivos de patrones de marcadores
│   ├── pattern-marker-0.patt
│   ├── pattern-marker-1.patt
│   ├── pattern-marker-2.patt
│   └── pattern-marker-3.patt
└── README.md              # Este archivo
```

## 🚀 Cómo Usar

### Opción 1: Hosting Local

1. **Clona o descarga este repositorio**

```bash
git clone [URL_DEL_REPOSITORIO]
cd AR-project-ucu
```

2. **Inicia un servidor HTTP local**

Puedes usar Python, Node.js, o cualquier servidor HTTP:

```bash
# Python 3
python -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000

# Node.js (con http-server instalado)
npx http-server -p 8000
```

3. **Abre en tu navegador móvil**

Visita `http://[TU_IP_LOCAL]:8000` desde tu teléfono (asegúrate de estar en la misma red WiFi).

### Opción 2: GitHub Pages

1. **Sube el proyecto a GitHub**
2. **Habilita GitHub Pages** en la configuración del repositorio (Settings → Pages)
3. **Accede desde tu móvil** a `https://[TU_USUARIO].github.io/[NOMBRE_REPOSITORIO]`

## 📱 Requisitos del Sistema

- **Navegador moderno** con soporte para:
  - WebGL
  - getUserMedia (acceso a cámara)
  - WebRTC
- **Recomendado**: Chrome o Firefox en Android, Safari en iOS
- **Conexión HTTPS** (requerida para acceso a cámara en producción)
- **Buena iluminación** para detección óptima de marcadores

## 🖨️ Preparación de Marcadores

### Imprimir Marcadores

1. **Abre** `markers-print.html` en tu navegador
2. **Imprime los 4 marcadores** en papel blanco de buena calidad
3. **Asegúrate de imprimir al 100% de escala** (sin ajustar tamaño)
4. **Mantén los bordes negros** visibles y completos

### Colocación Sugerida

- **Marcador 0**: Entrada principal del edificio
- **Marcador 1**: Biblioteca o sala de lectura
- **Marcador 2**: Sala principal o auditorio
- **Marcador 3**: Lugar emblemático del edificio

### Tips para Mejores Resultados

- Coloca los marcadores en superficies planas y mate (no vidrio)
- Evita reflejos y brillos en los marcadores
- Asegura buena iluminación en las áreas de los marcadores
- Mantén los marcadores lo más planos posible

## 🎮 Cómo Jugar

1. **Abre la aplicación** en tu navegador móvil
2. **Permite el acceso a la cámara** cuando se solicite
3. **Busca los marcadores AR** distribuidos por el edificio
4. **Apunta tu cámara** a cada marcador para revelar contenido 3D
5. **Lee las pistas** que aparecen con cada marcador
6. **Encuentra los 4 marcadores** para completar la búsqueda
7. **Descubre el tesoro final** y su significado

## 🎨 Contenido de Cada Marcador

### Marcador 0: La Entrada del Misterio 🏛️
- **Objeto 3D**: Cubo verde giratorio con cono dorado
- **Pista**: "Busca las pistas en los lugares donde el conocimiento florece"
- **Siguiente paso**: Dirígete a la biblioteca

### Marcador 1: Los Archivos Antiguos 📚
- **Objeto 3D**: Cilindro azul animado con toro rojo
- **Pista**: "Donde se reúnen las mentes, cerca del corazón del edificio"
- **Siguiente paso**: Busca la sala principal

### Marcador 2: El Corazón del Sacré Coeur 🗝️
- **Objeto 3D**: Esfera naranja con octaedro morado giratorio
- **Pista**: "El tesoro no es oro ni plata, es el conocimiento transmitido"
- **Siguiente paso**: Busca el último marcador

### Marcador 3: El Tesoro Revelado 💎
- **Objeto 3D**: Caja dorada giratoria con efecto de destellos
- **Revelación**: El verdadero tesoro es la educación impartida en el edificio
- **Final**: ¡Misión completada!

## 💻 Personalización

### Modificar Contenido 3D

Edita [ar-experience.html](ar-experience.html:86) en la sección de marcadores:

```html
<a-marker type="pattern" url="markers/pattern-marker-0.patt" id="marker-0" registerevents>
    <!-- Agrega tus propios objetos 3D aquí -->
    <a-box position="0 0.5 0" material="color: #4CAF50;"></a-box>
</a-marker>
```

### Cambiar Mensajes y Pistas

Modifica el objeto `gameState.markerData` en [ar-experience.html](ar-experience.html:263):

```javascript
markerData: {
    0: {
        name: "Tu Título",
        icon: "🎯",
        message: "Tu mensaje personalizado",
        clue: "Tu pista personalizada"
    }
}
```

### Agregar Más Marcadores

1. **Genera un nuevo patrón** en [AR.js Marker Training](https://ar-js-org.github.io/AR.js/three.js/examples/marker-training/examples/generator.html)
2. **Descarga el archivo .patt** y colócalo en la carpeta `markers/`
3. **Agrega el marcador** en el HTML:

```html
<a-marker type="pattern" url="markers/pattern-marker-4.patt" id="marker-4" registerevents>
    <!-- Tu contenido 3D -->
</a-marker>
```

4. **Actualiza el JavaScript** para incluir el nuevo marcador en `gameState`

## 🐛 Solución de Problemas

### La cámara no se activa
- Verifica que estés usando HTTPS (requerido para acceso a cámara)
- Comprueba los permisos de la cámara en tu navegador
- Prueba en modo incógnito para descartar problemas de permisos

### Los marcadores no se detectan
- Asegura buena iluminación
- Mantén el marcador plano y sin arrugas
- Ajusta la distancia (aprox. 30-50 cm)
- Verifica que los bordes negros estén completos

### El contenido 3D no aparece
- Abre la consola del navegador para ver errores
- Verifica que los archivos .patt estén en la ruta correcta
- Comprueba que WebGL esté habilitado

### El progreso no se guarda
- Verifica que LocalStorage esté habilitado
- En modo incógnito, el progreso no persiste entre sesiones
- Borra la caché si hay problemas de almacenamiento

## 📚 Recursos Adicionales

- **[Documentación de AR.js](https://ar-js-org.github.io/AR.js-Docs/)**
- **[A-Frame School](https://aframe.io/aframe-school/)** - Tutoriales de A-Frame
- **[Generador de Marcadores AR.js](https://ar-js-org.github.io/AR.js/three.js/examples/marker-training/examples/generator.html)**
- **[Componentes A-Frame](https://www.npmjs.com/search?q=aframe-component)** - Extensiones adicionales

## 🎓 Objetivos de Aprendizaje Cumplidos

- ✅ Comprensión de Realidad Aumentada basada en marcadores
- ✅ Integración de lógica de juego en JavaScript
- ✅ Detección de eventos de marcadores (markerFound, markerLost)
- ✅ Manejo de estado y progreso del usuario
- ✅ Creación de experiencias interactivas con feedback visual
- ✅ Trabajo con bibliotecas AR.js y A-Frame
- ✅ Animaciones 3D y entidades personalizadas

## 👥 Créditos

Proyecto desarrollado para el curso de Realidad Aumentada - Universidad Católica del Uruguay

**Tecnologías:**
- AR.js por Jerome Etienne
- A-Frame por Mozilla
- Patrones de marcadores generados con AR.js Marker Training Tool

## 📄 Licencia

Este proyecto es de código abierto y está disponible bajo la licencia MIT.

---

¡Disfruta de tu búsqueda del tesoro en AR! 🎉

Para preguntas o mejoras, abre un issue en el repositorio.
