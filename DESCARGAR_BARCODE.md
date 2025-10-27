# 📥 Cómo Descargar Marcadores BARCODE

## Problema

Los marcadores BARCODE generados por JavaScript no funcionan porque no coinciden con el formato que AR.js espera.

## Solución: Usar Marcadores BARCODE Oficiales

### Opción 1: Descargar desde GitHub (RECOMENDADO)

1. **Abre el repositorio oficial:**
   https://github.com/nicolocarpignoli/artoolkit-barcode-markers-collection

2. **Ve a la carpeta 3x3:**
   https://github.com/nicolocarpignoli/artoolkit-barcode-markers-collection/tree/master/3x3

3. **Descarga estos 3 archivos:**
   - `bch2_1.png` (para BARCODE valor 1)
   - `bch2_2.png` (para BARCODE valor 2)
   - `bch2_3.png` (para BARCODE valor 3)

4. **Guardarlos en tu proyecto:**
   ```bash
   # Guardar en la carpeta raíz con nombres simples:
   barcode-1.png
   barcode-2.png
   barcode-3.png
   ```

### Opción 2: Descargar Directamente (si GitHub funciona)

Usa estos comandos desde la raíz de tu proyecto:

```bash
# Descargar BARCODE 1
curl -o barcode-1.png https://raw.githubusercontent.com/nicolocarpignoli/artoolkit-barcode-markers-collection/master/3x3/bch2_1.png

# Descargar BARCODE 2
curl -o barcode-2.png https://raw.githubusercontent.com/nicolocarpignoli/artoolkit-barcode-markers-collection/master/3x3/bch2_2.png

# Descargar BARCODE 3
curl -o barcode-3.png https://raw.githubusercontent.com/nicolocarpignoli/artoolkit-barcode-markers-collection/master/3x3/bch2_3.png
```

### Opción 3: Usar Generador Online

1. Ve a: https://au.gmented.com/app/marker/marker.php
2. Selecciona:
   - Type: **Barcode**
   - Size: **3x3**
   - ID: **1** (luego 2, luego 3)
3. Click en **Generate**
4. Descarga la imagen
5. Repite para IDs 2 y 3

---

## Verificar que los archivos están correctos

Los marcadores BARCODE 3x3 correctos deberían verse así:

```
┌─────────────────┐
│ ████████████████│  Borde negro grueso
│ █              █│
│ █   ▓▓  ▓▓  ▓▓ █│  Patrón 3x3 interno
│ █   ▓▓  ▓▓  ▓▓ █│  (varía según el valor)
│ █   ▓▓  ▓▓  ▓▓ █│
│ █              █│
│ ████████████████│  Borde negro grueso
└─────────────────┘
```

Características:
- ✅ Borde negro grueso exterior
- ✅ Borde blanco interno
- ✅ Patrón 3x3 de cuadrados (blanco/negro)
- ✅ Cada valor (1, 2, 3) tiene un patrón único

---

## Después de Descargar

Una vez que tengas los 3 archivos en la raíz del proyecto:

```
/hiro.png         ✅ (ya existe)
/barcode-1.png    ✅ (nuevo)
/barcode-2.png    ✅ (nuevo)
/barcode-3.png    ✅ (nuevo)
```

Avísame y actualizaré `markers-print-new.html` para que use estas imágenes en lugar de generarlas con JavaScript.

---

## ⚠️ Si no puedes descargar

Si tienes problemas descargando desde GitHub (429 error), tengo estas alternativas:

### Alternativa 1: Usar solo HIRO
- Cambiar los 4 marcadores a usar HIRO
- Diferenciarlos por el diseño 3D que aparece

### Alternativa 2: Usar otros marcadores preset
AR.js tiene estos marcadores preset que funcionan:
- `hiro`
- `kanji`

Podríamos usar:
- Marcador 0: HIRO
- Marcador 1: KANJI
- Marcadores 2-3: Necesitarían pattern custom

### Alternativa 3: Crear patterns custom
- Usar: https://jeromeetienne.github.io/AR.js/three.js/examples/marker-training/examples/generator.html
- Generar marcadores custom
- Guardar archivos .patt

---

## 🎯 Acción Recomendada

**OPCIÓN MÁS FÁCIL:**

Usa el generador online:
1. Ve a: https://au.gmented.com/app/marker/marker.php
2. Genera BARCODE 3x3 con IDs 1, 2, 3
3. Descarga las 3 imágenes
4. Guárdalas como `barcode-1.png`, `barcode-2.png`, `barcode-3.png`
5. Ponlas en la raíz del proyecto
6. Avísame cuando estén listas

---

¿Puedes intentar descargar los marcadores? Avísame cuál método funciona o si necesitas otra alternativa.
