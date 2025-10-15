# 📑 Índice General del Proyecto

## 🏛️ Búsqueda del Tesoro en Realidad Aumentada

**Bienvenido al proyecto completo de la Búsqueda del Tesoro AR del Edificio Sacré Coeur.**

Este índice te ayudará a encontrar rápidamente la información que necesitas según tu rol.

---

## 🎭 Elige tu Rol

### 🎮 Soy un JUGADOR
**Quiero jugar la búsqueda del tesoro**

➡️ **Empieza aquí:** [GUIA_JUGADORES.md](GUIA_JUGADORES.md)

**Te ayudará con:**
- ✅ Cómo iniciar el juego
- ✅ Cómo usar la cámara AR
- ✅ Qué hacer en cada marcador
- ✅ Solución de problemas comunes
- ✅ Tips para completar el juego

**Tiempo de lectura:** 5 minutos

---

### 🎯 Soy un ORGANIZADOR
**Quiero organizar un evento con esta experiencia**

➡️ **Empieza aquí:** [GUIA_ORGANIZADORES.md](GUIA_ORGANIZADORES.md)

**Te ayudará con:**
- ✅ Planificación del evento
- ✅ Impresión y colocación de marcadores
- ✅ Configuración del servidor
- ✅ Gestión durante el evento
- ✅ Solución de problemas técnicos
- ✅ Material promocional

**Tiempo de lectura:** 15 minutos

---

### 👨‍💻 Soy un DESARROLLADOR
**Quiero personalizar o extender el proyecto**

➡️ **Empieza aquí:** [DEVELOPER_GUIDE.md](DEVELOPER_GUIDE.md)

**Te ayudará con:**
- ✅ Arquitectura del sistema
- ✅ Estructura de código
- ✅ Agregar nuevos marcadores
- ✅ Modificar objetos 3D
- ✅ Integrar nuevas funcionalidades
- ✅ Debugging y testing

**Tiempo de lectura:** 20 minutos

---

### ⚡ Quiero EMPEZAR YA
**Solo quiero probarlo rápidamente**

➡️ **Empieza aquí:** [QUICK_START.md](QUICK_START.md)

**Te ayudará con:**
- ✅ Setup en 5 minutos
- ✅ Comandos esenciales
- ✅ Testing rápido
- ✅ Soluciones instantáneas

**Tiempo de lectura:** 3 minutos

---

## 📚 Documentación Completa

### Documentos Principales

| Documento | Propósito | Audiencia | Tiempo |
|-----------|-----------|-----------|--------|
| **[README.md](README.md)** | Documentación general del proyecto | Todos | 10 min |
| **[GUIA_JUGADORES.md](GUIA_JUGADORES.md)** | Instrucciones para jugar | Jugadores | 5 min |
| **[GUIA_ORGANIZADORES.md](GUIA_ORGANIZADORES.md)** | Manual para organizar eventos | Organizadores | 15 min |
| **[DEVELOPER_GUIDE.md](DEVELOPER_GUIDE.md)** | Guía técnica avanzada | Desarrolladores | 20 min |
| **[QUICK_START.md](QUICK_START.md)** | Inicio rápido | Todos | 3 min |
| **[EXAMPLES.md](EXAMPLES.md)** | Ejemplos de código | Desarrolladores | 15 min |
| **[PROJECT_SUMMARY.md](PROJECT_SUMMARY.md)** | Resumen ejecutivo | Todos | 5 min |

### Archivos de la Aplicación

| Archivo | Descripción | Cuándo Usar |
|---------|-------------|-------------|
| **[index.html](index.html)** | Página de inicio | URL principal para usuarios |
| **[ar-experience.html](ar-experience.html)** | Experiencia AR principal | Automático desde index.html |
| **[markers-print.html](markers-print.html)** | Generador de marcadores | Para imprimir marcadores |

### Archivos de Marcadores

| Archivo | Marcador | Ubicación Sugerida |
|---------|----------|-------------------|
| **markers/pattern-marker-0.patt** | La Entrada | Hall de entrada |
| **markers/pattern-marker-1.patt** | La Biblioteca | Biblioteca/Sala de lectura |
| **markers/pattern-marker-2.patt** | La Sala Principal | Auditorio/Sala principal |
| **markers/pattern-marker-3.patt** | El Tesoro | Lugar emblemático |

---

## 🎯 Casos de Uso Frecuentes

### "Quiero probar la app AHORA"

1. Lee [QUICK_START.md](QUICK_START.md)
2. Ejecuta: `python3 -m http.server 8080`
3. Abre: `http://localhost:8080/markers-print.html`
4. Imprime marcadores
5. Abre en móvil: `http://TU_IP:8080`
6. ¡Juega!

**Tiempo total:** 5-10 minutos

---

### "Tengo que organizar un evento MAÑANA"

1. Lee [GUIA_ORGANIZADORES.md](GUIA_ORGANIZADORES.md) - Sección "1 Día Antes"
2. Imprime marcadores: `markers-print.html`
3. Configura servidor o deploy a GitHub Pages
4. Coloca marcadores en ubicaciones
5. Prueba el recorrido completo
6. Crea códigos QR

**Tiempo total:** 2-3 horas

---

### "Quiero enseñar a alguien a jugar"

1. Lee [GUIA_JUGADORES.md](GUIA_JUGADORES.md)
2. Comparte el link de la sección "Paso 2: Iniciar la Aventura"
3. Muéstrales cómo escanear el QR
4. Acompáñalos en el primer marcador
5. Déjalos explorar solos

**Tiempo total:** 10 minutos

---

### "Quiero agregar un 5to marcador"

1. Lee [DEVELOPER_GUIDE.md](DEVELOPER_GUIDE.md) - Sección "Agregar Nuevos Marcadores"
2. Lee [EXAMPLES.md](EXAMPLES.md) - Ver ejemplos de contenido 3D
3. Genera patrón en [AR.js Marker Training](https://ar-js-org.github.io/AR.js/three.js/examples/marker-training/examples/generator.html)
4. Edita [ar-experience.html](ar-experience.html)
5. Prueba

**Tiempo total:** 30-60 minutos

---

### "Necesito hacer deployment online"

1. Lee [README.md](README.md) - Sección "Cómo Usar"
2. O lee [QUICK_START.md](QUICK_START.md) - Sección "Deployment Ultra-Rápido"
3. Sigue las instrucciones de GitHub Pages
4. Comparte la URL resultante

**Tiempo total:** 5-10 minutos

---

## 🔍 Búsqueda Rápida por Tema

### Temas Técnicos

| Tema | Dónde Encontrarlo |
|------|-------------------|
| **Instalar servidor** | [QUICK_START.md](QUICK_START.md#-pasos-rpidos) |
| **Arquitectura del código** | [DEVELOPER_GUIDE.md](DEVELOPER_GUIDE.md#-arquitectura-del-sistema) |
| **Agregar marcadores** | [DEVELOPER_GUIDE.md](DEVELOPER_GUIDE.md#-agregar-nuevos-marcadores) |
| **Modificar 3D** | [EXAMPLES.md](EXAMPLES.md#-ejemplos-de-contenido-3d) |
| **Sistema de puntos** | [EXAMPLES.md](EXAMPLES.md#-ejemplos-de-lgica-de-juego) |
| **Debugging** | [DEVELOPER_GUIDE.md](DEVELOPER_GUIDE.md#-debugging-y-testing) |
| **Deployment** | [DEVELOPER_GUIDE.md](DEVELOPER_GUIDE.md#-deployment) |

### Temas de Uso

| Tema | Dónde Encontrarlo |
|------|-------------------|
| **Cómo jugar** | [GUIA_JUGADORES.md](GUIA_JUGADORES.md#-paso-4-jugar-la-bsqueda-del-tesoro) |
| **Permisos de cámara** | [GUIA_JUGADORES.md](GUIA_JUGADORES.md#-paso-3-permitir-acceso-a-la-cmara) |
| **Los 4 marcadores** | [GUIA_JUGADORES.md](GUIA_JUGADORES.md#-los-4-marcadores) |
| **Problemas comunes** | [GUIA_JUGADORES.md](GUIA_JUGADORES.md#-solucin-de-problemas) |
| **Tips de juego** | [GUIA_JUGADORES.md](GUIA_JUGADORES.md#-tips-para-tener-xito) |

### Temas de Organización

| Tema | Dónde Encontrarlo |
|------|-------------------|
| **Planificar evento** | [GUIA_ORGANIZADORES.md](GUIA_ORGANIZADORES.md#-checklist-pre-evento) |
| **Imprimir marcadores** | [GUIA_ORGANIZADORES.md](GUIA_ORGANIZADORES.md#-preparacin-de-marcadores) |
| **Colocar marcadores** | [GUIA_ORGANIZADORES.md](GUIA_ORGANIZADORES.md#-planificacin-de-ubicaciones) |
| **Configurar servidor** | [GUIA_ORGANIZADORES.md](GUIA_ORGANIZADORES.md#-configuracin-del-servidor) |
| **Durante el evento** | [GUIA_ORGANIZADORES.md](GUIA_ORGANIZADORES.md#-gestin-durante-el-evento) |
| **Material promocional** | [GUIA_ORGANIZADORES.md](GUIA_ORGANIZADORES.md#-material-adicional-recomendado) |

---

## 📊 Flujo Recomendado por Rol

### Para Organizadores
```
1. Lee PROJECT_SUMMARY.md (5 min)
   ↓
2. Lee GUIA_ORGANIZADORES.md (15 min)
   ↓
3. Sigue QUICK_START.md para probar (5 min)
   ↓
4. Planifica ubicaciones y materiales
   ↓
5. Consulta DEVELOPER_GUIDE.md si necesitas personalizar
   ↓
6. Organiza el evento
```

### Para Jugadores
```
1. Recibe URL o QR del organizador
   ↓
2. Lee primeras 2 secciones de GUIA_JUGADORES.md (2 min)
   ↓
3. Abre la app y sigue instrucciones en pantalla
   ↓
4. Si tienes problemas, consulta "Solución de Problemas"
   ↓
5. ¡Disfruta el juego!
```

### Para Desarrolladores
```
1. Lee PROJECT_SUMMARY.md (5 min)
   ↓
2. Lee README.md completo (10 min)
   ↓
3. Lee DEVELOPER_GUIDE.md (20 min)
   ↓
4. Revisa EXAMPLES.md para ideas (15 min)
   ↓
5. Clona y experimenta con el código
   ↓
6. Personaliza según necesites
```

---

## 🆘 Ayuda Rápida

### Problemas Comunes

| Problema | Solución Rápida | Dónde Leer Más |
|----------|----------------|----------------|
| **Cámara no funciona** | Verifica permisos en Configuración | [GUIA_JUGADORES.md](GUIA_JUGADORES.md#la-cmara-no-funciona) |
| **No detecta marcadores** | Mejora iluminación, ajusta distancia | [GUIA_JUGADORES.md](GUIA_JUGADORES.md#no-detecta-el-marcador) |
| **Puerto en uso** | Usa otro puerto: `python3 -m http.server 8081` | [QUICK_START.md](QUICK_START.md#-soluciones-instantneas) |
| **Perdí progreso** | Recarga la página, está guardado en LocalStorage | [GUIA_JUGADORES.md](GUIA_JUGADORES.md#perd-mi-progreso) |
| **Servidor no responde** | Verifica que esté corriendo, reinicia si es necesario | [GUIA_ORGANIZADORES.md](GUIA_ORGANIZADORES.md#el-servidor-no-responde) |

### Enlaces Útiles

- **[Generador de Marcadores AR.js](https://ar-js-org.github.io/AR.js/three.js/examples/marker-training/examples/generator.html)**
- **[Documentación AR.js](https://ar-js-org.github.io/AR.js-Docs/)**
- **[Documentación A-Frame](https://aframe.io/docs/)**
- **[Generador de QR Codes](https://www.qr-code-generator.com/)**

---

## 📞 Soporte

### ¿No encuentras lo que buscas?

1. **Busca en este índice** la sección relevante
2. **Usa Ctrl+F** en el documento correspondiente para buscar palabras clave
3. **Consulta el README.md** para información general
4. **Revisa los ejemplos** en EXAMPLES.md
5. **Contacta al organizador** del evento o al desarrollador

---

## ✅ Checklist General

### Antes de Empezar (Todos)
- [ ] He identificado mi rol (Jugador/Organizador/Desarrollador)
- [ ] He leído la guía correspondiente
- [ ] Tengo los requisitos técnicos necesarios
- [ ] He probado que mi dispositivo funciona

### Para Testing Rápido
- [ ] He leído QUICK_START.md
- [ ] He iniciado el servidor
- [ ] He impreso al menos un marcador
- [ ] He probado en mi dispositivo móvil

### Para Evento Real
- [ ] He leído GUIA_ORGANIZADORES.md completa
- [ ] He planificado las ubicaciones
- [ ] He impreso y colocado todos los marcadores
- [ ] He probado el recorrido completo
- [ ] He creado material promocional

### Para Desarrollo
- [ ] He leído DEVELOPER_GUIDE.md
- [ ] He revisado los EXAMPLES.md
- [ ] He clonado el repositorio
- [ ] He probado hacer cambios
- [ ] He documentado mis modificaciones

---

## 🎉 ¡Comienza tu Aventura!

Ahora que sabes dónde encontrar todo, **elige tu camino** y comienza:

- 🎮 **Jugadores:** → [GUIA_JUGADORES.md](GUIA_JUGADORES.md)
- 🎯 **Organizadores:** → [GUIA_ORGANIZADORES.md](GUIA_ORGANIZADORES.md)
- 👨‍💻 **Desarrolladores:** → [DEVELOPER_GUIDE.md](DEVELOPER_GUIDE.md)
- ⚡ **Todos:** → [QUICK_START.md](QUICK_START.md)

---

**Última actualización:** Octubre 2025
**Versión del proyecto:** 1.0
**Estado:** ✅ Completo y funcional

¡Que la búsqueda del tesoro sea exitosa! 🏛️💎✨
