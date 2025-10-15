# 🚀 Inicio Rápido - 5 Minutos

Guía express para tener tu búsqueda del tesoro AR funcionando en 5 minutos.

## ⚡ Pasos Rápidos

### 1. Inicia el Servidor (1 minuto)

Elige tu método preferido:

```bash
# Python 3 (más común)
python3 -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000

# Node.js
npx http-server -p 8000

# PHP
php -S localhost:8000
```

### 2. Encuentra tu IP Local (1 minuto)

**macOS/Linux:**
```bash
ifconfig | grep "inet " | grep -v 127.0.0.1
```

**Windows:**
```bash
ipconfig | findstr "IPv4"
```

Tu IP será algo como: `192.168.1.100`

### 3. Imprime los Marcadores (2 minutos)

1. Abre en tu computadora: `http://localhost:8000/markers-print.html`
2. Presiona el botón "Imprimir Marcadores"
3. Imprime en papel blanco, **escala 100%**
4. Corta los 4 marcadores

### 4. Prueba en tu Móvil (1 minuto)

1. En tu teléfono (conectado a la misma WiFi): abre `http://TU_IP_LOCAL:8000`
2. Presiona "Iniciar Búsqueda"
3. Permite acceso a la cámara
4. Apunta la cámara a cualquier marcador impreso

## 🎮 Testing Rápido Sin Imprimir

Si no puedes imprimir, puedes mostrar los marcadores en otra pantalla:

1. Abre `markers-print.html` en tu computadora
2. Abre la app AR en tu móvil
3. Apunta la cámara del móvil a los marcadores en la pantalla de la computadora

**Consejo:** Ajusta el brillo de la pantalla al 100% para mejor detección.

## ✅ Checklist de Problemas Comunes

- [ ] ¿El servidor está corriendo? (verifica que `http://localhost:8000` funcione)
- [ ] ¿Tu teléfono está en la misma red WiFi que tu computadora?
- [ ] ¿Permitiste acceso a la cámara en el navegador?
- [ ] ¿Hay buena iluminación en la habitación?
- [ ] ¿Los marcadores están planos y sin reflejos?

## 🐛 Soluciones Instantáneas

### "La cámara no se activa"
- **Solución:** Usa Chrome o Safari, acepta permisos cuando aparezca el popup

### "No detecta los marcadores"
- **Solución:** Acerca/aleja el teléfono (distancia ideal: 30-50cm)
- **Solución:** Mejora la iluminación

### "No se conecta desde el móvil"
- **Solución:** Verifica que uses la IP correcta (no uses localhost)
- **Solución:** Desactiva firewall temporalmente

## 📱 URLs Importantes

- **Landing Page:** `http://TU_IP:8000/`
- **Experiencia AR:** `http://TU_IP:8000/ar-experience.html`
- **Imprimir Marcadores:** `http://TU_IP:8000/markers-print.html`

## 🎯 Secuencia de Marcadores

Para testing secuencial:

1. **Marcador 0** (Cubo verde) → Pista: Busca la biblioteca
2. **Marcador 1** (Cilindro azul) → Pista: Ve a la sala principal
3. **Marcador 2** (Esfera naranja) → Pista: Busca el tesoro final
4. **Marcador 3** (Caja dorada) → ¡Tesoro encontrado! 🎉

## 🚀 Deployment Ultra-Rápido (GitHub Pages)

```bash
# En la carpeta del proyecto
git init
git add .
git commit -m "AR Treasure Hunt"
gh repo create ar-treasure-hunt --public --source=. --remote=origin --push

# Habilitar GitHub Pages
gh repo view --web
# Settings → Pages → Source: main → Save
```

En 2-3 minutos estará disponible en:
`https://TU_USUARIO.github.io/ar-treasure-hunt/`

## 💡 Pro Tips

1. **Testing Local Rápido:** Abre DevTools (F12) en el navegador y simula:
   ```javascript
   // En la consola
   onMarkerFound(0)
   onMarkerFound(1)
   onMarkerFound(2)
   onMarkerFound(3)
   ```

2. **Resetear Progreso:**
   ```javascript
   localStorage.clear()
   location.reload()
   ```

3. **Ver Estado del Juego:**
   ```javascript
   console.log(gameState)
   ```

## 📞 ¿Necesitas Ayuda?

- 📖 Guía completa: [README.md](README.md)
- 👨‍💻 Guía técnica: [DEVELOPER_GUIDE.md](DEVELOPER_GUIDE.md)
- 🐛 Reportar problemas: Abre un issue en GitHub

---

**¡Listo! En 5 minutos deberías estar cazando tesoros en AR.** 🎉

Si algo no funciona, consulta el [README.md](README.md) completo para solución de problemas detallada.
