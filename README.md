# 🎵 Doble Péndulo Musical

Un simulador interactivo de péndulo doble con síntesis de audio en tiempo real que convierte el movimiento caótico en música.

![Doble Péndulo Musical](https://img.shields.io/badge/Status-Active-brightgreen) ![HTML5](https://img.shields.io/badge/HTML5-Canvas-orange) ![Audio](https://img.shields.io/badge/Audio-WebAudio_API-blue)

## ✨ Características

### 🔬 Simulación Física
- **Integración Runge-Kutta de 4to orden** para máxima precisión
- **Conservación de energía** con monitoreo de deriva energética
- **Sistema de amortiguamiento** físicamente realista
- **Control de balance** unificado para longitudes L1 y L2
- **Interacción drag-and-drop** para posicionamiento inicial

### 🎼 Síntesis de Audio
- **Modo Tonal**: Velocidades angulares → frecuencias de sonido
- **Modo Percusión**: Detección de picos → golpes de batería sintética
- **Parámetros ajustables**: Volumen, frecuencias base, sensibilidad
- **Audio en tiempo real** usando Web Audio API

### 🎛️ Controles Avanzados
- **Balance de Longitudes**: Control unificado L1 ↔ L2
- **Masas independientes**: m₁ y m₂ ajustables
- **Gravedad variable**: Desde 0.1 hasta 20.0 m/s²
- **Velocidades angulares**: Configuración inicial de ω₁ y ω₂
- **Paso de integración Δt**: Control de precisión/rendimiento

### 📱 Interfaz
- **Modo pantalla completa** optimizado
- **Trazado de trayectorias** con colores diferenciados
- **Información en tiempo real** de estado físico
- **Efectos visuales** sincronizados con audio

## 🚀 Uso

### Instalación Local
```bash
# Clonar el repositorio
git clone <repository-url>
cd pendulo

# Servir localmente
python3 -m http.server 8000

# Acceder en navegador
# http://localhost:8000/musical_double_pendulum_improved.html
```

### Controles Básicos
- **▶**: Iniciar simulación
- **⏹**: Detener simulación  
- **⟲**: Reiniciar a posición inicial
- **🗑**: Limpiar trazas
- **♪**: Activar/desactivar audio tonal
- **🥁**: Activar/desactivar percusión
- **⛶**: Modo pantalla completa

### Parámetros Físicos
- **Balance**: -1.0 (L₁ mayor) ↔ +1.0 (L₂ mayor)
- **Masas**: 0.2 - 5.0 kg
- **Gravedad**: 0.1 - 20.0 m/s²
- **Fricción**: 0 - 2.0 (amortiguamiento)
- **ω₁, ω₂**: -6.0 a +6.0 rad/s (velocidades iniciales)

### Parámetros de Audio
- **Volumen**: 0 - 1.0
- **Frecuencias Base**: 200 - 1000 Hz
- **Sensibilidad**: 0.5 - 5.0 (mapeo ω → frecuencia)
- **Umbral Percusión**: 0.2 - 3.0 rad/s
- **Cooldown**: 50 - 500 ms entre golpes

## 🎯 Casos de Uso Educativos

### Física
- **Sistemas dinámicos** y teoría del caos
- **Conservación de energía** en sistemas mecánicos
- **Ecuaciones diferenciales** y métodos numéricos
- **Acoplamiento** entre osciladores

### Matemáticas
- **Integración numérica** (Runge-Kutta)
- **Sistemas no lineales** y sensibilidad a condiciones iniciales
- **Análisis de estabilidad** y puntos de equilibrio

### Arte/Música
- **Sonificación** de datos físicos
- **Síntesis de audio** procedimental
- **Patrones rítmicos** emergentes del caos
- **Visualización** de sistemas dinámicos

## 🔧 Detalles Técnicos

### Integración Numérica
```javascript
// Método Runge-Kutta 4to orden para precisión
rk4Step(dt) {
  // Calcula k1, k2, k3, k4
  // Actualiza θ₁, θ₂, ω₁, ω₂
}
```

### Síntesis de Audio
```javascript
// Mapeo velocidad angular → frecuencia
const freqMult = 1 + Math.abs(omega) * sensitivity * 0.1;
const freq = baseFreq * freqMult;
```

### Control de Balance
```javascript
// L1 y L2 balanceados desde un parámetro
this.l1 = baseLength - (balance * maxDelta);
this.l2 = baseLength + (balance * maxDelta);
```

## 🎛️ Configuraciones Recomendadas

### Caos Clásico
- Balance: 0.0 (L₁ = L₂)
- Masas: m₁ = m₂ = 1.0 kg
- Gravedad: 9.81 m/s²
- Sin fricción
- Posición inicial: Vertical hacia arriba

### Oscilación Suave
- Balance: -0.5 (L₁ > L₂)
- Fricción: 0.1
- Velocidades iniciales pequeñas
- Audio tonal activado

### Ritmos Complejos
- Balance: 0.8 (L₂ >> L₁)
- Masas diferentes: m₁ = 2.0, m₂ = 0.5
- Percusión activada
- Umbral bajo: 0.5 rad/s

## 🔍 Monitoreo del Sistema

### Conservación de Energía
- **Deriva < 0.1%**: ✅ Correcto
- **Deriva 0.1-1%**: ⚠️ Deriva menor
- **Deriva > 1%**: ❌ Deriva alta

### Recomendaciones Δt
- **Movimiento lento**: Δt = 0.020s
- **Movimiento rápido**: Δt = 0.005s
- **Máxima precisión**: Δt = 0.001s

## 🤝 Contribuciones

Este proyecto demuestra la aplicación de:
- Métodos numéricos avanzados
- Síntesis de audio procedural
- Interfaces interactivas HTML5/Canvas
- Visualización de sistemas dinámicos

## 📚 Referencias

- Ecuaciones del doble péndulo: Lagrangian mechanics
- Integración RK4: Numerical Methods for ODEs
- Web Audio API: MDN Web Docs
- Teoría del caos: Nonlinear Dynamics and Chaos

## 📄 Licencia

Proyecto educativo y de demostración.

---

🤖 **Generado con [Claude Code](https://claude.ai/code)**

Co-Authored-By: Claude <noreply@anthropic.com>