# 📝 Ejemplos de Código - Extensiones Comunes

Ejemplos prácticos de cómo extender y personalizar tu experiencia AR.

## 🎨 Ejemplos de Contenido 3D

### 1. Crear un Cofre del Tesoro Animado

```html
<a-marker type="pattern" url="markers/pattern-marker-3.patt" id="marker-3" registerevents>
    <!-- Base del cofre -->
    <a-box position="0 0.2 0"
           width="0.6" height="0.4" depth="0.4"
           material="color: #8B4513; metalness: 0.5; roughness: 0.8">
    </a-box>

    <!-- Tapa del cofre (animada) -->
    <a-box position="0 0.5 -0.15"
           width="0.6" height="0.1" depth="0.2"
           rotation="-30 0 0"
           material="color: #654321; metalness: 0.5; roughness: 0.8"
           animation="property: rotation; to: 0 0 0; dur: 2000; dir: alternate; loop: true">
    </a-box>

    <!-- Monedas brillantes saliendo -->
    <a-sphere position="0 0.6 0" radius="0.05"
              material="color: #FFD700; metalness: 0.9; roughness: 0.1"
              animation="property: position; to: 0 1.2 0; dur: 1500; dir: alternate; loop: true; easing: easeOutQuad">
    </a-sphere>
    <a-sphere position="0.1 0.6 0.1" radius="0.05"
              material="color: #FFD700; metalness: 0.9; roughness: 0.1"
              animation="property: position; to: 0.1 1.2 0.1; dur: 1500; dir: alternate; loop: true; delay: 200; easing: easeOutQuad">
    </a-sphere>
    <a-sphere position="-0.1 0.6 -0.1" radius="0.05"
              material="color: #FFD700; metalness: 0.9; roughness: 0.1"
              animation="property: position; to: -0.1 1.2 -0.1; dur: 1500; dir: alternate; loop: true; delay: 400; easing: easeOutQuad">
    </a-sphere>

    <!-- Texto flotante -->
    <a-text value="TESORO"
            position="-0.5 1.5 0"
            color="#FFD700"
            align="center"
            width="2"
            animation="property: position; to: -0.5 1.7 0; dur: 2000; dir: alternate; loop: true">
    </a-text>
</a-marker>
```

### 2. Libro Flotante que se Abre

```html
<a-marker type="pattern" url="markers/pattern-marker-1.patt" id="marker-1" registerevents>
    <a-entity position="0 0.5 0">
        <!-- Cubierta izquierda -->
        <a-box position="-0.15 0 0"
               width="0.3" height="0.4" depth="0.02"
               material="color: #8B0000; metalness: 0.3"
               rotation="0 -20 0"
               animation="property: rotation; to: 0 -60 0; dur: 3000; dir: alternate; loop: true">
        </a-box>

        <!-- Cubierta derecha -->
        <a-box position="0.15 0 0"
               width="0.3" height="0.4" depth="0.02"
               material="color: #8B0000; metalness: 0.3"
               rotation="0 20 0"
               animation="property: rotation; to: 0 60 0; dur: 3000; dir: alternate; loop: true">
        </a-box>

        <!-- Páginas -->
        <a-box position="0 0 0"
               width="0.28" height="0.38" depth="0.1"
               material="color: #FFFACD">
        </a-box>

        <!-- Partículas de conocimiento -->
        <a-entity position="0 0.5 0">
            <a-text value="📚" position="0 0 0" width="1"
                    animation="property: position; to: 0 0.8 0; dur: 2000; loop: true; dir: alternate">
            </a-text>
        </a-entity>
    </a-entity>

    <a-text value="BIBLIOTECA"
            position="-0.8 1.5 0"
            color="#FFFFFF"
            align="center"
            width="2">
    </a-text>
</a-marker>
```

### 3. Portal Dimensional

```html
<a-marker type="pattern" url="markers/pattern-marker-2.patt" id="marker-2" registerevents>
    <!-- Anillo exterior -->
    <a-torus position="0 0.5 0"
             radius="0.5"
             radius-tubular="0.05"
             material="color: #00FFFF; metalness: 0.8; emissive: #00FFFF; emissiveIntensity: 0.5"
             rotation="90 0 0"
             animation="property: rotation; to: 90 360 0; loop: true; dur: 3000; easing: linear">
    </a-torus>

    <!-- Anillo medio -->
    <a-torus position="0 0.5 0"
             radius="0.35"
             radius-tubular="0.04"
             material="color: #FF00FF; metalness: 0.8; emissive: #FF00FF; emissiveIntensity: 0.5"
             rotation="90 0 0"
             animation="property: rotation; to: 90 -360 0; loop: true; dur: 2000; easing: linear">
    </a-torus>

    <!-- Centro brillante -->
    <a-circle position="0 0.5 0"
              radius="0.25"
              material="color: #FFFFFF; opacity: 0.8; shader: flat"
              rotation="-90 0 0"
              animation="property: material.opacity; to: 0.3; dur: 1000; dir: alternate; loop: true">
    </a-circle>

    <!-- Estrellas -->
    <a-sphere position="0.3 0.5 0" radius="0.02" material="color: #FFFFFF; emissive: #FFFFFF"
              animation="property: scale; to: 1.5 1.5 1.5; dur: 500; dir: alternate; loop: true">
    </a-sphere>
    <a-sphere position="-0.3 0.5 0" radius="0.02" material="color: #FFFFFF; emissive: #FFFFFF"
              animation="property: scale; to: 1.5 1.5 1.5; dur: 500; dir: alternate; loop: true; delay: 250">
    </a-sphere>

    <a-text value="PORTAL"
            position="-0.5 1.2 0"
            color="#00FFFF"
            align="center"
            width="2">
    </a-text>
</a-marker>
```

## 🔊 Ejemplos de Audio

### 1. Sonido Ambiente por Marcador

```javascript
// Agregar en ar-experience.html
const markerSounds = {
    0: new Audio('./sounds/entrance.mp3'),
    1: new Audio('./sounds/library.mp3'),
    2: new Audio('./sounds/hall.mp3'),
    3: new Audio('./sounds/treasure.mp3')
};

// Modificar el componente registerevents
AFRAME.registerComponent('registerevents', {
    init: function () {
        const marker = this.el;
        const markerId = parseInt(marker.id.split('-')[1]);

        marker.addEventListener('markerFound', function() {
            // Reproducir sonido específico
            if (markerSounds[markerId]) {
                markerSounds[markerId].play();
            }
            onMarkerFound(markerId);
        });

        marker.addEventListener('markerLost', function() {
            // Pausar sonido
            if (markerSounds[markerId]) {
                markerSounds[markerId].pause();
                markerSounds[markerId].currentTime = 0;
            }
        });
    }
});
```

### 2. Música de Fondo

```javascript
// Agregar al inicio de startExperience()
function startExperience() {
    document.getElementById('instructions-overlay').style.display = 'none';
    loadProgress();

    // Música de fondo
    const bgMusic = new Audio('./sounds/ambient-background.mp3');
    bgMusic.loop = true;
    bgMusic.volume = 0.2;
    bgMusic.play().catch(e => console.log('Autoplay blocked:', e));
}
```

## 🎯 Ejemplos de Lógica de Juego

### 1. Sistema de Puntos

```javascript
// Agregar al gameState
const gameState = {
    markersFound: new Set(),
    totalMarkers: 4,
    score: 0,
    timeStarted: null,
    markerData: { /* ... */ }
};

// Modificar onMarkerFound
function onMarkerFound(markerId) {
    if (gameState.markersFound.has(markerId)) return;

    // Iniciar timer en el primer marcador
    if (gameState.markersFound.size === 0) {
        gameState.timeStarted = Date.now();
    }

    gameState.markersFound.add(markerId);

    // Calcular puntos basados en velocidad
    const timeElapsed = (Date.now() - gameState.timeStarted) / 1000; // segundos
    const speedBonus = Math.max(0, 100 - Math.floor(timeElapsed / 10));
    const points = 100 + speedBonus;

    gameState.score += points;

    // Actualizar UI
    document.getElementById('score-display').textContent = `Puntos: ${gameState.score}`;

    saveProgress();
    playSound('success');
    updateUI();
    showNotification(markerId, points);

    if (gameState.markersFound.size === gameState.totalMarkers) {
        setTimeout(() => showTreasureModal(), 3000);
    }
}
```

### 2. Sistema de Hints (Pistas)

```javascript
// Agregar botón de pista en el HUD
function addHintSystem() {
    const hintButton = document.createElement('button');
    hintButton.id = 'hint-btn';
    hintButton.innerHTML = '💡 Pista';
    hintButton.className = 'close-btn';
    hintButton.style.position = 'fixed';
    hintButton.style.bottom = '20px';
    hintButton.style.right = '20px';
    hintButton.onclick = showHint;
    document.body.appendChild(hintButton);
}

function showHint() {
    // Encontrar el siguiente marcador sin descubrir
    const nextMarker = [0, 1, 2, 3].find(id => !gameState.markersFound.has(id));

    if (nextMarker !== undefined) {
        const hint = gameState.markerData[nextMarker].clue;
        alert(`Pista: ${hint}`);

        // Opcional: Reducir puntos por usar pista
        gameState.score = Math.max(0, gameState.score - 10);
        updateScoreDisplay();
    } else {
        alert('¡Ya encontraste todos los marcadores!');
    }
}
```

### 3. Modo Multijugador Local (Competencia)

```javascript
// Tabla de clasificación local
const leaderboard = {
    scores: JSON.parse(localStorage.getItem('leaderboard') || '[]'),

    addScore(playerName, score, time) {
        this.scores.push({
            name: playerName,
            score: score,
            time: time,
            date: new Date().toISOString()
        });

        // Ordenar por puntuación
        this.scores.sort((a, b) => b.score - a.score);

        // Mantener top 10
        this.scores = this.scores.slice(0, 10);

        localStorage.setItem('leaderboard', JSON.stringify(this.scores));
    },

    getTopScores() {
        return this.scores;
    }
};

// Al completar el juego
function showTreasureModal() {
    const playerName = prompt('¡Felicitaciones! Ingresa tu nombre:') || 'Anónimo';
    const finalTime = (Date.now() - gameState.timeStarted) / 1000;

    leaderboard.addScore(playerName, gameState.score, finalTime);

    // Mostrar clasificación
    const topScores = leaderboard.getTopScores();
    const leaderboardHTML = topScores.map((entry, index) =>
        `<div>${index + 1}. ${entry.name} - ${entry.score} pts (${entry.time.toFixed(1)}s)</div>`
    ).join('');

    document.getElementById('treasure-modal').classList.add('show');
    // Agregar clasificación al modal...
}
```

## 📱 Ejemplos de UI Mejorada

### 1. Barra de Progreso Animada

```html
<!-- Agregar al HUD -->
<div id="progress-bar-animated" style="width: 100%; background: rgba(0,0,0,0.5); height: 10px; margin-top: 10px; border-radius: 5px; overflow: hidden;">
    <div id="progress-fill" style="width: 0%; height: 100%; background: linear-gradient(90deg, #667eea, #764ba2); transition: width 0.5s ease;"></div>
</div>
```

```javascript
// Actualizar en updateUI()
function updateUI() {
    const progress = (gameState.markersFound.size / gameState.totalMarkers) * 100;
    document.getElementById('progress-fill').style.width = `${progress}%`;

    document.getElementById('found-count').textContent = gameState.markersFound.size;

    gameState.markersFound.forEach(markerId => {
        const statusEl = document.getElementById(`status-${markerId}`);
        if (statusEl) {
            statusEl.classList.add('found');
            statusEl.querySelector('.marker-icon').textContent = '✅';
        }
    });
}
```

### 2. Contador de Tiempo

```html
<!-- Agregar al HUD -->
<div id="timer" style="font-size: 1.5em; margin-top: 10px; text-align: center;">
    ⏱️ <span id="time-display">00:00</span>
</div>
```

```javascript
// Agregar timer
let timerInterval;

function startTimer() {
    timerInterval = setInterval(() => {
        if (gameState.timeStarted) {
            const elapsed = Math.floor((Date.now() - gameState.timeStarted) / 1000);
            const minutes = Math.floor(elapsed / 60).toString().padStart(2, '0');
            const seconds = (elapsed % 60).toString().padStart(2, '0');
            document.getElementById('time-display').textContent = `${minutes}:${seconds}`;
        }
    }, 1000);
}

// Llamar en startExperience()
function startExperience() {
    document.getElementById('instructions-overlay').style.display = 'none';
    loadProgress();
    startTimer();
}
```

### 3. Efectos de Confetti al Ganar

```javascript
// Agregar esta función
function launchConfetti() {
    const duration = 3000;
    const animationEnd = Date.now() + duration;
    const colors = ['#667eea', '#764ba2', '#FFD700', '#FF6B6B'];

    (function frame() {
        const confetti = document.createElement('div');
        confetti.style.position = 'fixed';
        confetti.style.width = '10px';
        confetti.style.height = '10px';
        confetti.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
        confetti.style.left = Math.random() * window.innerWidth + 'px';
        confetti.style.top = '-10px';
        confetti.style.borderRadius = '50%';
        confetti.style.zIndex = '9999';
        confetti.style.transition = 'all 3s ease-in-out';

        document.body.appendChild(confetti);

        setTimeout(() => {
            confetti.style.top = window.innerHeight + 'px';
            confetti.style.transform = `rotate(${Math.random() * 360}deg)`;
        }, 10);

        setTimeout(() => confetti.remove(), 3000);

        if (Date.now() < animationEnd) {
            requestAnimationFrame(frame);
        }
    })();
}

// Llamar en showTreasureModal()
function showTreasureModal() {
    playSound('victory');
    launchConfetti();
    document.getElementById('treasure-modal').classList.add('show');
}
```

## 🌐 Integración con APIs

### 1. Compartir en Redes Sociales

```javascript
function shareOnSocial(platform) {
    const url = encodeURIComponent(window.location.href);
    const text = encodeURIComponent(`¡Completé la Búsqueda del Tesoro AR en ${(Date.now() - gameState.timeStarted) / 1000}s con ${gameState.score} puntos!`);

    const shareUrls = {
        twitter: `https://twitter.com/intent/tweet?text=${text}&url=${url}`,
        facebook: `https://www.facebook.com/sharer/sharer.php?u=${url}`,
        whatsapp: `https://wa.me/?text=${text}%20${url}`
    };

    window.open(shareUrls[platform], '_blank', 'width=600,height=400');
}

// Agregar botones en el modal final
```

### 2. Guardar Progreso en la Nube (Firebase)

```javascript
// Agregar Firebase SDK en el HTML
// <script src="https://www.gstatic.com/firebasejs/9.x.x/firebase-app.js"></script>
// <script src="https://www.gstatic.com/firebasejs/9.x.x/firebase-database.js"></script>

// Configurar Firebase
const firebaseConfig = {
    // Tu configuración
};

firebase.initializeApp(firebaseConfig);
const database = firebase.database();

// Guardar progreso
function saveProgressToCloud(userId) {
    database.ref('users/' + userId).set({
        markersFound: [...gameState.markersFound],
        score: gameState.score,
        lastUpdated: Date.now()
    });
}

// Cargar progreso
function loadProgressFromCloud(userId) {
    database.ref('users/' + userId).once('value').then((snapshot) => {
        const data = snapshot.val();
        if (data) {
            gameState.markersFound = new Set(data.markersFound);
            gameState.score = data.score;
            updateUI();
        }
    });
}
```

## 🎓 Ejercicios Propuestos

### Nivel Básico
1. Cambiar los colores de los objetos 3D
2. Modificar los textos y mensajes
3. Agregar un nuevo marcador simple

### Nivel Intermedio
4. Implementar el sistema de puntos
5. Agregar un temporizador visual
6. Crear nuevas animaciones para los objetos 3D

### Nivel Avanzado
7. Implementar el sistema de clasificación
8. Agregar modelos 3D externos (.gltf)
9. Crear un sistema de logros/insignias
10. Implementar compartir en redes sociales

---

¿Implementaste alguna de estas extensiones? ¡Comparte tu proyecto en GitHub!
