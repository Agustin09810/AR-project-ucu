# 📱 Qué Debería Pasar - Guía de Prueba

## 🧪 PRUEBA 1: test-simple.html (PRIMERO PRUEBA ESTO)

### Paso 1: Abrir el archivo
1. Abre **`test-simple.html`** en tu navegador móvil
2. Si estás en desktop, súbelo a Vercel o usa un servidor local con HTTPS

### Paso 2: Permitir cámara
- El navegador te pedirá permiso para usar la cámara
- Click en **"Permitir"**

### Paso 3: Qué DEBERÍAS ver

#### ✅ Si TODO funciona correctamente:

**En pantalla:**
- Un panel negro en la esquina superior izquierda
- Texto: "✅ Cámara: OK"
- Estado de marcadores: "⏹️ marker-hiro - buscando..."
- **El video de tu cámara de fondo** (IMPORTANTE: DEBES VER LA CÁMARA)

**Cuando apuntas al marcador HIRO:**
1. **Aparece un CUBO AZUL 3D flotando sobre el marcador** (girando)
2. **Aparece texto blanco "HIRO"** flotando
3. El panel cambia a: "✅ marker-hiro - ENCONTRADO!" (en verde)
4. **Aparece una alerta**: "¡Marcador encontrado! marker-hiro"
5. En la consola del navegador: "✅ MARCADOR ENCONTRADO: marker-hiro"

**Cuando mueves la cámara (pierdes el marcador):**
1. El cubo azul DESAPARECE
2. El panel cambia a: "⏹️ marker-hiro - buscando..."
3. En la consola: "❌ MARCADOR PERDIDO: marker-hiro"

### Paso 4: Abrir la consola del navegador

**En móvil (Chrome Android):**
- Abre Chrome en desktop
- Ve a `chrome://inspect`
- Conecta el móvil por USB
- Click en "inspect" en tu página

**En desktop:**
- Presiona F12 o clic derecho > "Inspeccionar"
- Ve a la pestaña "Console"

**Qué deberías ver en la consola:**
```
📱 Página cargada - AR.js Test Simple
👀 Abre la consola para ver los eventos
✅ Cámara inicializada
🔧 Componente registerevents iniciado para: marker-hiro
🔧 Componente registerevents iniciado para: marker-barcode-1
🔧 Componente registerevents iniciado para: marker-barcode-2
```

**Cuando detecta un marcador:**
```
✅ MARCADOR ENCONTRADO: marker-hiro
```

---

## ❌ Si NO funciona - Diagnóstico

### Problema 1: No veo la cámara (pantalla negra)

**Posibles causas:**
- ❌ No diste permiso a la cámara
- ❌ Estás usando HTTP en lugar de HTTPS (Chrome requiere HTTPS para cámara)
- ❌ Tu navegador no soporta getUserMedia

**Soluciones:**
1. Verifica permisos del navegador: Configuración > Sitios > Cámara
2. Usa HTTPS:
   - Sube a Vercel
   - O usa `localhost` (que funciona sin HTTPS)
   - O usa `npx http-server -S` (servidor local con HTTPS)
3. Prueba en otro navegador (Chrome, Firefox, Safari)

### Problema 2: Veo la cámara pero NO aparece nada al apuntar al marcador

**Posibles causas:**
- ❌ El marcador impreso NO es el correcto
- ❌ Mala iluminación
- ❌ Marcador arrugado o reflejos
- ❌ Marcador muy pequeño o muy lejos
- ❌ Estás apuntando por la parte de atrás del marcador

**Soluciones:**
1. **Imprime los marcadores correctos:**
   - Abre `markers-print-new.html`
   - Imprime en escala 100%
   - Usa el marcador HIRO (cuadrado con patrón dentro)

2. **Condiciones de detección:**
   - Buena iluminación (luz natural o blanca)
   - Marcador plano (sin arrugas)
   - Superficie mate (NO vidrio)
   - Distancia: 20-50 cm de la cámara
   - Marcador tamaño mínimo: 5x5 cm

3. **Verifica en consola:**
   - Si ves "🔧 Componente registerevents iniciado" = código cargó OK
   - Si NO ves "✅ MARCADOR ENCONTRADO" = AR.js no detecta el marcador

### Problema 3: Aparece el cubo pero NO la notificación/alert

**Causa:**
- El código visual (A-Frame) funciona
- Pero los eventos JavaScript NO se disparan

**Solución:**
- Esto indica que falta `registerevents` component o hay error en el código
- Verifica errores en la consola (pestaña Console)

---

## 🎯 Qué debería pasar con ar-experience.html

Si **test-simple.html** funciona correctamente, entonces `ar-experience.html` debería:

1. **Pantalla de inicio:**
   - Overlay con instrucciones
   - Botón "Entendido, comenzar!"

2. **Después de click en comenzar:**
   - Se oculta el overlay
   - Se activa la cámara
   - Ves el video de la cámara
   - Panel de progreso arriba: "Progreso: 0/4 marcadores"

3. **Al detectar marcador 0 (HIRO):**
   - Aparece cubo verde 3D con cono dorado
   - Texto "INICIO" flotando
   - **Aparece notificación modal blanca** con:
     - Icono: 🏛️
     - Título: "La Entrada del Misterio"
     - Mensaje y pista
   - Panel actualiza: "Progreso: 1/4 marcadores"
   - Icono del marcador cambia a ✅

4. **Al detectar marcador 1 (BARCODE 1):**
   - Aparece cilindro azul con torus rojo
   - Texto "BIBLIOTECA"
   - Notificación con icono 📚
   - Progreso: 2/4

5. **Al detectar los 4 marcadores:**
   - Aparece modal grande de victoria
   - "¡FELICITACIONES!"
   - Icono tesoro 🎉💎🏆

---

## 🔍 Checklist de Diagnóstico

Completa este checklist:

- [ ] Abrí `test-simple.html` en el navegador
- [ ] Di permiso a la cámara
- [ ] Veo el video de mi cámara de fondo
- [ ] Veo el panel negro con información
- [ ] Imprimí el marcador HIRO correctamente
- [ ] Apunto el marcador a la cámara (distancia 20-50cm)
- [ ] Hay buena iluminación
- [ ] **Aparece el cubo azul 3D sobre el marcador** ✅ o ❌
- [ ] Aparece la alerta "¡Marcador encontrado!"
- [ ] Abrí la consola y veo los logs
- [ ] En consola veo: "✅ MARCADOR ENCONTRADO"

---

## 📸 Cómo hacer una buena prueba

### Marcador HIRO (para test-simple.html):

1. Descarga la imagen oficial: https://raw.githubusercontent.com/AR-js-org/AR.js/master/data/images/hiro.png
2. Imprime en tamaño A4 o muestra en otra pantalla
3. Asegúrate que el marcador tiene:
   - Borde negro grueso
   - Patrón H en el centro
   - Cuadrado perfecto (no deformado)

### Condiciones ideales:

```
☀️ Iluminación: Buena (natural o LED blanco)
📏 Distancia: 20-50 cm
📐 Ángulo: Perpendicular (90 grados)
📄 Superficie: Plana y mate
🔲 Tamaño: Mínimo 5x5 cm
```

---

## 🆘 Si nada funciona

Si después de todo esto sigue sin funcionar:

1. **Prueba en otro dispositivo:**
   - Otro celular
   - Tablet
   - Laptop con webcam

2. **Prueba en otro navegador:**
   - Chrome (recomendado)
   - Firefox
   - Safari (iOS)

3. **Verifica versión del navegador:**
   - Chrome: v90+
   - Firefox: v88+
   - Safari: v14+

4. **Prueba ejemplos oficiales online:**
   - https://stemkoski.github.io/AR.js-examples/index.html
   - Si estos NO funcionan = problema con tu dispositivo/navegador
   - Si estos SÍ funcionan = problema con nuestro código

5. **Envíame:**
   - Screenshot de la pantalla
   - Screenshot de la consola (con errores)
   - Navegador y versión
   - Dispositivo (marca/modelo)

---

## ✅ Prueba Exitosa - Qué hacer después

Si `test-simple.html` funciona:

1. ✅ Confirmamos que AR.js funciona en tu dispositivo
2. ✅ Confirmamos que la cámara funciona
3. ✅ Confirmamos que los marcadores se detectan
4. ✅ Ahora podemos debuggear `ar-experience.html`

**Siguiente paso:**
- Compara `test-simple.html` (que funciona) con `ar-experience.html`
- Identifica diferencias
- Ajusta `ar-experience.html` para que funcione igual

---

**IMPORTANTE:** Antes de hacer CUALQUIER otra cosa, **prueba test-simple.html** y confirma que:
1. Ves la cámara ✅
2. Aparece el cubo 3D cuando apuntas al marcador ✅

Si eso funciona, el resto es solo ajustar el código.
Si eso NO funciona, necesitamos resolver el problema básico primero.
