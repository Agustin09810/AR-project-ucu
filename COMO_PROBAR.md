# 🚀 Cómo Probar la Aplicación AR - Guía Rápida

## ✅ PASO 1: Obtener el Marcador HIRO

**¡Ya lo tienes!** El marcador HIRO está en tu proyecto:

📁 **Ubicación:** `tecnologias_vr/markers/hiro.png`

### Opciones para usar el marcador:

#### Opción A: Imprimirlo 🖨️
1. Abre el archivo `tecnologias_vr/markers/hiro.png`
2. Imprímelo en papel blanco (tamaño A4)
3. Escala: 100% (sin reducir ni ampliar)
4. Recorta dejando el borde negro completo

#### Opción B: Mostrarlo en otra pantalla 📱
1. Abre `tecnologias_vr/markers/hiro.png` en otro dispositivo
2. Muéstralo en pantalla completa
3. Apunta tu cámara a esa pantalla
4. **Importante:** Ajusta el brillo de la pantalla (ni muy bajo ni muy alto)

#### Opción C: Copiar a la raíz del proyecto
```bash
# Desde la raíz del proyecto
cp tecnologias_vr/markers/hiro.png ./hiro.png
```

---

## ✅ PASO 2: Preparar el entorno de prueba

### Si pruebas en MÓVIL:

**Opción 1: Usar Vercel (RECOMENDADO)**
```bash
# Desplegar a Vercel
git add .
git commit -m "Add test-simple.html for debugging"
git push
```
- Vercel despliega automáticamente
- HTTPS está habilitado por defecto
- Abre la URL: `tu-proyecto.vercel.app/test-simple.html`

**Opción 2: Servidor local con ngrok**
```bash
# Terminal 1: Iniciar servidor local
python3 -m http.server 8000

# Terminal 2: Exponer con ngrok
npx ngrok http 8000
```
- Copia la URL HTTPS que te da ngrok
- Ábrela en tu móvil

### Si pruebas en DESKTOP/LAPTOP:

**Opción 1: Servidor local simple**
```bash
# Desde la raíz del proyecto
python3 -m http.server 8000

# Abre en navegador:
# http://localhost:8000/test-simple.html
```

**Opción 2: Abrir directo (solo si funciona)**
- Abre `test-simple.html` directamente en el navegador
- Algunos navegadores modernos lo permiten

---

## ✅ PASO 3: Probar test-simple.html

### 1. Abrir la aplicación

**En móvil:**
- Abre Chrome o Safari
- Ve a: `https://tu-url/test-simple.html`

**En desktop:**
- Abre Chrome o Firefox
- Ve a: `http://localhost:8000/test-simple.html`

### 2. Permitir cámara

Cuando aparezca el popup:
- Click en **"Permitir"** o **"Allow"**
- Si no aparece, verifica permisos en: Configuración > Sitio > Cámara

### 3. Verificar que la cámara funciona

Deberías ver:
- ✅ Video de tu cámara de fondo
- ✅ Panel negro arriba con información
- ✅ Texto: "✅ Cámara: OK"
- ✅ Estado de marcadores: "⏹️ buscando..."

**Si NO ves la cámara:**
- ❌ Verifica que diste permiso
- ❌ Verifica que estás usando HTTPS (o localhost)
- ❌ Prueba en otro navegador

### 4. Apuntar al marcador HIRO

**Setup:**
1. Ten el marcador HIRO listo (impreso o en otra pantalla)
2. Buena iluminación (luz natural o LED blanco)
3. Distancia: 20-40 cm entre cámara y marcador
4. Ángulo: Perpendicular (90 grados)

**Qué hacer:**
1. Sostén el marcador frente a la cámara
2. Mantén el marcador plano (sin arrugas)
3. Asegúrate que se ve todo el marcador en pantalla
4. Muévelo lentamente hasta que se detecte

### 5. ¿Qué DEBERÍA pasar?

✅ **ÉXITO - Si ves esto, funciona:**
1. **Aparece un CUBO AZUL 3D** flotando sobre el marcador
2. El cubo está GIRANDO
3. **Aparece texto "HIRO"** encima del cubo
4. **Aparece un ALERT popup**: "¡Marcador encontrado! marker-hiro"
5. Panel cambia a: "✅ marker-hiro - ENCONTRADO!" (en verde)

❌ **FALLA - Si esto pasa, hay problema:**
1. No aparece ningún cubo
2. No cambia el estado en el panel
3. No aparece el alert

---

## ✅ PASO 4: Verificar la consola del navegador

### Cómo abrir la consola:

**En Desktop:**
- **Chrome/Firefox:** Presiona `F12` o clic derecho > "Inspeccionar"
- **Safari:** Cmd+Option+I
- Ve a la pestaña **"Console"**

**En Móvil (Android + Chrome):**
1. En tu computadora, abre Chrome
2. Ve a: `chrome://inspect`
3. Conecta tu móvil por USB
4. Habilita "Depuración USB" en el móvil
5. Click en "inspect" junto a tu página
6. Se abre DevTools con la consola

**En Móvil (iOS + Safari):**
1. En iPhone: Configuración > Safari > Avanzado > Web Inspector: ON
2. Conecta iPhone a Mac
3. En Mac Safari: Develop > [Tu iPhone] > [Tu página]
4. Se abre Web Inspector

### Qué deberías ver en la consola:

**Al cargar la página:**
```
📱 Página cargada - AR.js Test Simple
👀 Abre la consola para ver los eventos
✅ Cámara inicializada
🔧 Componente registerevents iniciado para: marker-hiro
🔧 Componente registerevents iniciado para: marker-barcode-1
🔧 Componente registerevents iniciado para: marker-barcode-2
```

**Al detectar el marcador:**
```
✅ MARCADOR ENCONTRADO: marker-hiro
```

**Al perder el marcador:**
```
❌ MARCADOR PERDIDO: marker-hiro
```

**Si ves errores en rojo:**
- Copia el error completo
- Busca la línea que dice el problema
- Esto indica qué está fallando

---

## ✅ PASO 5: Pruebas con diferentes marcadores

Si **HIRO funciona**, prueba los otros:

### Marcador BARCODE 1

1. Abre `markers-print-new.html` en navegador
2. Verás el marcador generado para BARCODE 1
3. Imprímelo o muéstralo en pantalla
4. Apunta la cámara

**Qué debería pasar:**
- Aparece **CILINDRO ROJO** con torus
- Texto "BARCODE 1"
- Alert: "¡Marcador encontrado! marker-barcode-1"

### Marcador BARCODE 2

Mismo proceso, deberías ver:
- **ESFERA VERDE**
- Texto "BARCODE 2"

---

## 🐛 Troubleshooting - Problemas Comunes

### Problema 1: "No veo la cámara (pantalla negra)"

**Causas posibles:**
- ❌ Permisos de cámara denegados
- ❌ Usando HTTP en lugar de HTTPS
- ❌ Navegador no compatible
- ❌ Cámara ocupada por otra app

**Soluciones:**
1. **Verificar permisos:**
   - Chrome: click en 🔒 junto a la URL > Permisos
   - Asegúrate que "Cámara" está en "Permitir"

2. **Usar HTTPS:**
   - Despliega a Vercel (tiene HTTPS)
   - O usa `localhost` (funciona sin HTTPS)
   - O usa ngrok para túnel HTTPS

3. **Probar otro navegador:**
   - Chrome (recomendado)
   - Firefox
   - Safari (en iOS)

4. **Cerrar otras apps:**
   - Cierra apps que usen la cámara (Zoom, Skype, etc.)

### Problema 2: "Veo cámara pero marcador NO se detecta"

**Causas posibles:**
- ❌ Marcador incorrecto (no es el HIRO oficial)
- ❌ Mala iluminación
- ❌ Marcador arrugado o con reflejos
- ❌ Muy cerca o muy lejos
- ❌ Ángulo incorrecto

**Soluciones:**
1. **Usar marcador correcto:**
   - Debe ser `tecnologias_vr/markers/hiro.png`
   - Impreso en escala 100%
   - Con borde negro completo

2. **Mejorar iluminación:**
   - Usa luz natural (cerca de ventana)
   - O luz LED blanca (no amarilla)
   - Evita sombras sobre el marcador

3. **Condiciones óptimas:**
   - Distancia: 20-40 cm
   - Marcador plano (sin arrugas)
   - Todo el marcador visible en cámara
   - Ángulo perpendicular (90°)

4. **Si imprimiste:**
   - Papel blanco (no reciclado gris)
   - Impresión nítida (tinta negra intensa)
   - Sin brillos (papel mate)

5. **Si muestras en pantalla:**
   - Brillo medio (ni muy bajo ni muy alto)
   - Pantalla limpia (sin huellas)
   - Evita reflejos de luces

### Problema 3: "Aparece cubo pero NO el alert/notificación"

**Causa:**
- El componente visual (A-Frame) funciona
- Pero los eventos JavaScript NO se disparan

**Solución:**
1. Abre la consola y busca errores
2. Verifica que se vea: "🔧 Componente registerevents iniciado"
3. Si NO aparece, hay error en el script
4. Revisa errores en rojo en la consola

### Problema 4: "Cubo aparece pero muy distorsionado"

**Causa:**
- Problemas de calibración de cámara
- Marcador no plano

**Solución:**
- Asegura que el marcador esté completamente plano
- Mejora la iluminación
- Ajusta la distancia

---

## 📊 Tabla de Resultados Esperados

| Acción | Resultado Esperado | Si NO pasa |
|--------|-------------------|-----------|
| Abrir test-simple.html | Ves video de cámara | Problema de permisos/HTTPS |
| Panel muestra "✅ Cámara: OK" | Cámara funciona | Revisar consola de errores |
| Apuntar a HIRO | Cubo azul aparece | Marcador incorrecto o mala luz |
| Cubo visible | Alert popup aparece | Error en JavaScript |
| Panel actualiza a "ENCONTRADO!" | Evento JavaScript funciona | Verificar consola |
| Consola: "✅ MARCADOR ENCONTRADO" | Sistema completo OK | ✅ Todo funciona |

---

## ✅ Lista de Verificación Final

Antes de probar, asegúrate de tener:

- [ ] Archivo `test-simple.html` listo
- [ ] Marcador HIRO (de `tecnologias_vr/markers/hiro.png`)
- [ ] Marcador impreso O mostrado en otra pantalla
- [ ] Servidor HTTPS (Vercel) O localhost
- [ ] Buena iluminación en la habitación
- [ ] Permisos de cámara listos para dar
- [ ] Consola del navegador abierta (para logs)
- [ ] Otro dispositivo/navegador para probar (backup)

---

## 🎯 Objetivos de la Prueba

✅ **OBJETIVO MÍNIMO:**
- Ver la cámara funcionando
- Ver el cubo azul al apuntar a HIRO

✅ **OBJETIVO IDEAL:**
- Ver la cámara
- Cubo azul aparece
- Alert popup aparece
- Panel actualiza a "ENCONTRADO!"
- Consola muestra logs correctos

Si logras el **objetivo mínimo**, ya confirmamos que:
1. ✅ AR.js funciona en tu dispositivo
2. ✅ La cámara funciona
3. ✅ Los marcadores se detectan
4. ✅ A-Frame renderiza correctamente

El siguiente paso sería ajustar `ar-experience.html` para que funcione igual.

---

## 📸 Ayuda Visual - Cómo sostener el marcador

```
        📱 (Cámara de tu celular)
         |
         | 20-40 cm
         |
         ↓
    ┌─────────┐
    │  HIRO   │  ← Marcador plano
    │ Marker  │
    └─────────┘
```

**Posición correcta:**
- Marcador paralelo al suelo (o a la cámara)
- Sin inclinar
- Todo el marcador visible en la cámara
- Bordes del marcador dentro del frame

---

## 🆘 Si NADA funciona después de todo esto

1. **Toma screenshots:**
   - Pantalla de la aplicación
   - Consola del navegador (con errores si hay)

2. **Anota información:**
   - Dispositivo: (ej: iPhone 13, Samsung S21, Mac)
   - Navegador: (ej: Chrome 120, Safari 17)
   - URL que usaste: (ej: localhost:8000 o vercel.app)
   - ¿Ves la cámara?: SÍ/NO
   - ¿Aparece el cubo?: SÍ/NO

3. **Prueba ejemplo oficial:**
   - Abre: https://ar-js-org.github.io/AR.js/aframe/examples/marker-based/basic.html
   - ¿Funciona?: SÍ/NO
   - Si NO funciona = problema con tu dispositivo/navegador
   - Si SÍ funciona = problema con nuestro código

4. **Comparte los resultados**
   - Con esa info puedo ayudarte mejor

---

**¡IMPORTANTE!** Empieza SIEMPRE con `test-simple.html` antes de probar `ar-experience.html`.

Si `test-simple.html` funciona = el problema está en `ar-experience.html` y es fácil de arreglar.

Si `test-simple.html` NO funciona = necesitamos resolver el setup básico primero.

🎯 **¡Mucha suerte con las pruebas!**
