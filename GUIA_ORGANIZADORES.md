# 🎯 Guía para Organizadores - Búsqueda del Tesoro AR

Esta guía está diseñada para quienes van a **organizar y coordinar** la experiencia de búsqueda del tesoro en Realidad Aumentada.

## 📋 Checklist Pre-Evento

### 1 Semana Antes

- [ ] **Probar la aplicación completa** en al menos 2 dispositivos móviles diferentes
- [ ] **Identificar las ubicaciones** exactas para colocar los 4 marcadores
- [ ] **Verificar iluminación** en cada ubicación (debe ser buena, sin sombras fuertes)
- [ ] **Confirmar acceso WiFi** en todo el edificio (si usas servidor local)
- [ ] **Decidir método de deployment** (servidor local vs online)
- [ ] **Preparar materiales de impresión** (papel, impresora, plastificado opcional)

### 3 Días Antes

- [ ] **Imprimir los marcadores** en papel de buena calidad
- [ ] **Plastificar marcadores** (opcional pero recomendado para durabilidad)
- [ ] **Crear carteles de instrucciones** para cada ubicación
- [ ] **Preparar cinta adhesiva/soporte** para fijar marcadores
- [ ] **Configurar servidor** (si usas servidor local)
- [ ] **Crear códigos QR** con las URLs de acceso

### 1 Día Antes

- [ ] **Colocar marcadores** en las ubicaciones planificadas
- [ ] **Verificar que todos los marcadores se detectan correctamente**
- [ ] **Probar el recorrido completo** (tiempo estimado: 15-20 min)
- [ ] **Documentar ubicaciones exactas** con fotos/coordenadas
- [ ] **Preparar soporte técnico** (tener laptop disponible)
- [ ] **Crear hoja de registro** de participantes (opcional)

## 🗺️ Planificación de Ubicaciones

### Criterios para Elegir Ubicaciones

#### ✅ Ubicación Ideal
- Iluminación natural o artificial buena y uniforme
- Superficie plana y vertical (pared, puerta, pizarra)
- Altura adecuada (120-160 cm del suelo)
- Espacio libre de al menos 1.5 metros frente al marcador
- Sin reflejos de vidrios o superficies brillantes
- Accesible durante todo el evento
- Flujo moderado de personas (no demasiado congestionado)

#### ❌ Ubicación a Evitar
- Lugares muy oscuros o con luz irregular
- Superficies curvas o irregulares
- Lugares con mucho tráfico que bloquean la vista
- Áreas restringidas o que se cierran temporalmente
- Cerca de ventanas con luz solar directa (crea reflejos)
- Superficies brillantes o de vidrio

### Ubicaciones Sugeridas en el Edificio Sacré Coeur

#### Marcador 0: La Entrada del Misterio 🏛️
**Ubicación:** Hall de entrada principal
- **Dónde:** Pared lateral derecha al entrar
- **Altura:** 140 cm del suelo
- **Descripción:** Primera parada lógica del recorrido
- **Cartel:** "🔍 INICIO DE LA AVENTURA - Escanea para comenzar"

#### Marcador 1: Los Archivos Antiguos 📚
**Ubicación:** Biblioteca o sala de lectura
- **Dónde:** Cerca del escritorio de información o entrada
- **Altura:** 130 cm del suelo
- **Descripción:** Zona con libros y conocimiento
- **Cartel:** "📖 BIBLIOTECA ANTIGUA - La sabiduría te espera"

#### Marcador 2: El Corazón del Sacré Coeur 🗝️
**Ubicación:** Sala de reuniones o auditorio principal
- **Dónde:** Pared lateral junto a la entrada
- **Altura:** 140 cm del suelo
- **Descripción:** Punto central del edificio
- **Cartel:** "🏛️ CORAZÓN DEL EDIFICIO - Donde todos se reúnen"

#### Marcador 3: El Tesoro Revelado 💎
**Ubicación:** Lugar emblemático (capilla, sala histórica, etc.)
- **Dónde:** Lugar con significado especial
- **Altura:** 140 cm del suelo
- **Descripción:** Destino final con mensaje importante
- **Cartel:** "✨ DESTINO FINAL - El tesoro te aguarda"

## 🖨️ Preparación de Marcadores

### Impresión

1. **Abrir:** `http://localhost:8080/markers-print.html`
2. **Configurar impresora:**
   - Papel: Blanco, 80g o más
   - Calidad: Alta (600 dpi o superior)
   - Escala: **100% (CRÍTICO)**
   - Color: Blanco y negro está bien
   - Márgenes: Mínimos

3. **Verificar antes de imprimir:**
   - Los cuadrados negros deben verse nítidos
   - El borde negro debe ser continuo
   - Tamaño aproximado: 10-15 cm por lado

### Montaje Recomendado

**Opción 1: Plastificado (Recomendado)**
- Plastificar cada marcador con funda transparente
- Ventajas: Durabilidad, resistencia al agua, reutilizable
- Fijar con cinta de doble cara o adhesivo removible

**Opción 2: Enmarcado**
- Colocar en marco con vidrio antirreflejo
- Ventajas: Profesional, protegido, fácil de colgar
- Desventaja: Posibles reflejos si el vidrio no es mate

**Opción 3: Cartón Rígido**
- Pegar en cartón pluma o foam board
- Ventajas: Económico, fácil de transportar
- Fijar con tachuelas o cinta adhesiva fuerte

### Instalación en el Lugar

```
┌─────────────────────────────────────┐
│                                     │
│    [Cartel con Instrucciones]       │
│                                     │
│         140 cm del suelo            │
│    ┌─────────────────────┐         │
│    │                     │         │
│    │    MARCADOR AR      │         │
│    │                     │         │
│    └─────────────────────┘         │
│                                     │
│    "Mantén 30-50 cm de distancia"  │
│                                     │
└─────────────────────────────────────┘
```

## 🌐 Configuración del Servidor

### Opción A: Servidor Local (Recomendado para Interiores)

**Ventajas:**
- No requiere internet externo
- Control total
- Sin límites de ancho de banda

**Desventajas:**
- Requiere computadora encendida durante el evento
- Todos deben estar en la misma red WiFi

**Setup:**

```bash
# En la carpeta del proyecto
cd /Users/agustinlorenzo/Documents/Projects/AR-project-ucu/

# Iniciar servidor (elegir puerto disponible)
python3 -m http.server 8080

# Obtener tu IP local
ifconfig | grep "inet " | grep -v 127.0.0.1
# Ejemplo: 10.13.9.95
```

**URL para compartir:** `http://[TU_IP]:8080`

**Checklist del día:**
- [ ] Laptop conectada a corriente
- [ ] Conectada al WiFi del edificio
- [ ] Servidor iniciado
- [ ] URL probada en al menos un dispositivo móvil
- [ ] Laptop en modo "No dormir"

### Opción B: GitHub Pages (Recomendado para Exterior/Larga Duración)

**Ventajas:**
- No requiere computadora durante el evento
- Accesible desde cualquier lugar con internet
- URL permanente y fácil de compartir

**Desventajas:**
- Requiere configuración previa
- Depende de internet

**Setup:**

```bash
# En la carpeta del proyecto
git init
git add .
git commit -m "Búsqueda del Tesoro AR - Sacré Coeur"

# Crear repo en GitHub (usa gh CLI o web)
gh repo create ar-sacre-coeur --public --source=. --push

# Habilitar GitHub Pages
# 1. Ve a Settings → Pages
# 2. Source: main branch
# 3. Save
# 4. Espera 2-3 minutos
```

**URL resultante:** `https://[TU_USUARIO].github.io/ar-sacre-coeur/`

### Crear Códigos QR (Altamente Recomendado)

```bash
# Usando sitios web gratuitos:
# 1. qr-code-generator.com
# 2. qrcode.tec-it.com
# 3. qr.io

# Crear QR para:
- URL principal de la app
- URL de cada marcador (para acceso directo)
- URL de ayuda/soporte
```

**Imprimir QR y colocar:**
- En la entrada del evento
- Junto al Marcador 0
- En material promocional

## 👥 Gestión Durante el Evento

### Rol del Organizador

**Antes de que lleguen participantes:**
- [ ] Verificar que todos los marcadores estén en su lugar
- [ ] Probar la app en 2-3 dispositivos diferentes
- [ ] Verificar que el servidor esté corriendo (si aplica)
- [ ] Tener laptop de soporte disponible
- [ ] Preparar hoja de registro de participantes

**Durante el evento:**
- [ ] Dar bienvenida y explicación breve (2 min)
- [ ] Ayudar con problemas técnicos
- [ ] Monitorear que los marcadores sigan en su lugar
- [ ] Registrar participantes y tiempos (opcional)
- [ ] Tomar fotos/videos para documentación

**Después del evento:**
- [ ] Recoger marcadores
- [ ] Recopilar feedback de participantes
- [ ] Documentar problemas técnicos
- [ ] Actualizar estadísticas de uso

### Script de Bienvenida (2 minutos)

```
"¡Bienvenidos a la Búsqueda del Tesoro en Realidad Aumentada!

Van a explorar el Edificio Sacré Coeur usando sus celulares
para encontrar 4 marcadores AR escondidos por el edificio.

¿Cómo funciona?
1. Escaneen este código QR [mostrar] para abrir la app
2. Permitan acceso a la cámara cuando lo pida
3. Busquen los 4 marcadores distribuidos por el edificio
4. Cuando encuentren uno, apunten la cámara hacia él
5. Verán aparecer objetos 3D y recibirán pistas
6. Sigan las pistas hasta encontrar el tesoro final

Tips importantes:
- Mantengan 30-50 cm de distancia del marcador
- Asegúrense de tener buena iluminación
- Si tienen problemas, estoy aquí para ayudar

El recorrido toma aproximadamente 15-20 minutos.
¡Que comience la aventura! 🎉"
```

## 🔧 Solución de Problemas Comunes

### "La cámara no se activa"

**Causas:**
- Navegador sin permisos de cámara
- Conexión no es HTTPS (en producción)
- Cámara en uso por otra app

**Soluciones:**
1. Ir a Settings → Permisos → Cámara → Permitir
2. Cerrar otras apps que usen la cámara
3. Probar en navegador diferente (Chrome recomendado)
4. Si usas servidor local, asegurar que la URL use IP local

### "No detecta el marcador"

**Causas:**
- Iluminación insuficiente o irregular
- Marcador arrugado o dañado
- Distancia incorrecta
- Marcador impreso a escala incorrecta

**Soluciones:**
1. Mejorar iluminación (encender luces, abrir cortinas)
2. Acercar/alejar el dispositivo (30-50 cm ideal)
3. Sostener el marcador más plano
4. Verificar que el marcador tenga todos sus bordes negros visibles
5. Limpiar la lente de la cámara

### "El servidor no responde"

**Causas:**
- Computadora en modo suspensión
- Cambio de IP del servidor
- Sobrecarga de conexiones

**Soluciones:**
1. Verificar que el servidor siga corriendo
2. Reiniciar el servidor si es necesario
3. Verificar la IP con `ifconfig` (puede cambiar)
4. Reducir número de usuarios simultáneos

### "La app está lenta"

**Causas:**
- Dispositivo antiguo
- Muchas apps abiertas
- Conexión lenta

**Soluciones:**
1. Cerrar apps en segundo plano
2. Reiniciar el navegador
3. Limpiar caché del navegador
4. Reducir calidad de renderizado (editar ar-experience.html)

## 📊 Métricas y Evaluación

### Datos para Recopilar

**Durante el evento:**
- Número de participantes
- Tiempo promedio de completado
- Marcadores que causaron más problemas
- Dispositivos/navegadores usados
- Tasa de completado (cuántos terminan vs abandonan)

**Encuesta post-evento (opcional):**
1. ¿Qué tan fácil fue usar la aplicación? (1-5)
2. ¿La historia fue interesante? (1-5)
3. ¿Los marcadores se detectaron bien? (1-5)
4. ¿Qué mejorarías?
5. ¿Recomendarías esta experiencia?

### Plantilla de Registro

```
BÚSQUEDA DEL TESORO AR - REGISTRO
Fecha: _______________

Participante | Hora Inicio | Hora Fin | Tiempo Total | Marcadores Encontrados | Completado | Notas
-------------|-------------|----------|--------------|----------------------|------------|-------
1.           |             |          |              |                      | Sí/No      |
2.           |             |          |              |                      | Sí/No      |
3.           |             |          |              |                      | Sí/No      |

Problemas técnicos:
_______________________________________________________________

Feedback general:
_______________________________________________________________
```

## 🎁 Material Adicional Recomendado

### Señalización Física

**Carteles para cada marcador:**
```
┌─────────────────────────────────────┐
│                                     │
│         🎯 ESTACIÓN [N]/4           │
│                                     │
│     [Nombre del Marcador]           │
│                                     │
│  1. Abre la app AR en tu celular    │
│  2. Apunta la cámara a este cuadro  │
│  3. Mantén 30-50 cm de distancia    │
│  4. Descubre la pista oculta        │
│                                     │
│  [Código QR de la app]              │
│                                     │
│  ¿Problemas? Busca al organizador   │
│                                     │
└─────────────────────────────────────┘
```

### Material Promocional

**Volante/Poster del evento:**
```
╔═══════════════════════════════════════╗
║                                       ║
║   🏛️ BÚSQUEDA DEL TESORO AR 💎        ║
║                                       ║
║   Explora el Edificio Sacré Coeur     ║
║   con Realidad Aumentada              ║
║                                       ║
║   📅 Fecha: [___________]             ║
║   ⏰ Hora: [___________]              ║
║   📍 Inicio: Hall Principal           ║
║   ⏱️ Duración: 15-20 minutos          ║
║                                       ║
║   Requisitos:                         ║
║   • Smartphone con cámara             ║
║   • Conexión WiFi/Internet            ║
║   • Espíritu aventurero 🎮            ║
║                                       ║
║   [Código QR]                         ║
║                                       ║
║   ¡Encuentra los 4 marcadores         ║
║   y descubre el tesoro oculto!        ║
║                                       ║
╚═══════════════════════════════════════╝
```

## 📞 Lista de Contactos de Emergencia

**Antes del evento, preparar:**

```
CONTACTOS DE SOPORTE TÉCNICO

Desarrollador/Soporte:
Nombre: _______________
Tel: __________________
Email: ________________

IT del edificio:
Nombre: _______________
Tel: __________________

Backup de servidor:
URL alternativa: _______________
Laptop backup: Sí/No

Impresora cercana (por si hay que reimprimir):
Ubicación: _______________
Contacto: _______________
```

## ✅ Checklist Final del Día del Evento

**2 Horas Antes:**
- [ ] Servidor corriendo y probado
- [ ] Todos los marcadores en su lugar
- [ ] Laptop de soporte lista con batería/corriente
- [ ] Códigos QR impresos y visibles
- [ ] Carteles de instrucciones colocados
- [ ] Material de registro preparado
- [ ] Celular de prueba funcionando

**30 Minutos Antes:**
- [ ] Recorrido de prueba completo
- [ ] Verificar iluminación en cada ubicación
- [ ] Preparar área de bienvenida
- [ ] Tener URLs anotadas y visibles
- [ ] Celular del organizador cargado

**Durante:**
- [ ] Dar bienvenida a cada grupo
- [ ] Ayudar con problemas técnicos
- [ ] Registrar participantes
- [ ] Monitorear marcadores
- [ ] Recopilar feedback

**Al Finalizar:**
- [ ] Recoger todos los marcadores
- [ ] Apagar servidor
- [ ] Recopilar hojas de registro
- [ ] Tomar notas de mejoras
- [ ] Agradecer a participantes

## 🎯 Tips de Oro para Organizadores

1. **Siempre ten un dispositivo de prueba** para verificar que todo funcione
2. **Llega 1 hora antes** para setup y pruebas finales
3. **Ten marcadores de backup** impresos por si se dañan
4. **Documenta todo con fotos/videos** para mejorar futuras ediciones
5. **Pide feedback honesto** a los primeros usuarios
6. **Ten paciencia** - la tecnología a veces falla
7. **Mantén energía positiva** - tu entusiasmo es contagioso
8. **Aprende de cada evento** para mejorar el siguiente

---

**¿Preguntas?** Consulta [DEVELOPER_GUIDE.md](DEVELOPER_GUIDE.md) para aspectos técnicos o [README.md](README.md) para información general.

¡Éxito con tu evento! 🎉
