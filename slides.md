---
theme: penguin
layout: intro
transition: slide-left
---

# Distribuciones de Probabilidad 📊

## Aplicaciones en Marketing Digital y Métricas de Rendimiento

Unidad II - Estadística Aplicada

<div v-click class="text-sm opacity-75 mt-6">
Bernoulli • Binomial • Multinomial • Poisson • Normal • Exponencial • Weibull
</div>

---
layout: presenter
presenterImage: 
---

# Introducción al Caso

<v-clicks>

**Contexto:** Una agencia de marketing digital gestiona múltiples campañas simultáneas

Los datos registrados permiten **modelar fenómenos aleatorios**:
- 👆 Clics en anuncios
- 💰 Conversiones (ventas, registros, descargas)
- ⏱️ Tiempo entre interacciones
- ⚠️ Errores técnicos en landing pages

</v-clicks>

---
layout: text-window
transition: fade
---

# Tipos de Distribuciones

<div v-motion
  :initial="{ opacity: 0, y: 20 }"
  :enter="{ opacity: 1, y: 0 }"
  class="text-lg mt-6">
Clasificación fundamental en probabilidad
</div>

::window::
  
╔══════════════════════════════════════╗
║   DISTRIBUCIONES DE PROBABILIDAD    ║
╠══════════════════════════════════════╣
║                                      ║
║  📊 DISCRETAS                        ║
║  └─ Conteo de eventos                ║
║     (0, 1, 2, 3, ...)                ║
║                                      ║
║  📈 CONTINUAS                        ║
║  └─ Mediciones en rango              ║
║     (tiempo, distancia, ...)         ║
║                                      ║
╚══════════════════════════════════════╝

---
layout: intro
class: text-center
---

# PARTE I

## Distribuciones Discretas 🎲

<div v-after class="text-sm opacity-75 mt-4">
Bernoulli • Binomial • Multinomial • Poisson
</div>

---
layout: text-image
media: 
transition: slide-up
---

# 1. Distribución de Bernoulli 

<div class="text-sm opacity-75 mb-4">
Experimento con solo dos resultados posibles
</div>

<v-clicks depth="2">

- **Contexto Real**
  - Usuario ve un anuncio en redes sociales
  - ✅ Hace clic (éxito) o ❌ No hace clic (fracaso)

- **Fórmula**
  - $P(X = x) = p^x (1-p)^{1-x}$, donde $x \in \{0,1\}$

- **Ejemplo Práctico**
  - CTR histórico = 8% → $p = 0.08$
  - $P(\text{clic}) = 0.08$
  - $P(\text{no clic}) = 0.92$

</v-clicks>

---

# 2. Distribución Binomial 📊

<div class="text-sm opacity-75 mb-4">
Número de éxitos en n ensayos independientes
</div>

<v-clicks>

### Fórmula
$$P(X = k) = \binom{n}{k} p^k (1-p)^{n-k}$$

### Caso Práctico
- 10 usuarios ven el anuncio ($n = 10$)
- Probabilidad de clic $p = 0.08$
- ¿Probabilidad de exactamente 2 clics?

$$P(X = 2) = \binom{10}{2} (0.08)^2 (0.92)^8 \approx \boxed{0.1478}$$

**Respuesta: 14.78% de probabilidad**

</v-clicks>

---
zoom: 0.9
---

# 3. Distribución Multinomial 🎯

<div class="bg-blue-50 p-4 rounded mb-4">
Extensión de la binomial a múltiples categorías
</div>

<v-clicks depth="2">

- **Escenario:** Un anuncio genera 3 tipos de respuesta
  - 👆 Clic: $p_1 = 0.08$
  - 👁️ Visualización sin clic: $p_2 = 0.85$
  - 🚫 Reporte como spam: $p_3 = 0.07$

- **Fórmula**
$$P(X_1=x_1, X_2=x_2, X_3=x_3) = \frac{n!}{x_1! x_2! x_3!} p_1^{x_1} p_2^{x_2} p_3^{x_3}$$

- **Cálculo:** 20 usuarios → 2 clics, 17 vistas, 1 spam
$$P = \frac{20!}{2! \cdot 17! \cdot 1!} (0.08)^2 (0.85)^{17} (0.07)^1 \approx \boxed{0.0323}$$

</v-clicks>

---
layout: text-image
media: 
reverse: true
---

# 4. Distribución de Poisson ⚡

<v-clicks>

### Características
- Eventos raros en intervalo fijo
- Tasa promedio conocida: $\lambda$
- Eventos independientes

### Fórmula
$$P(X = k) = \frac{e^{-\lambda} \lambda^k}{k!}$$

### Ejemplo
- Promedio: 5 conversiones/hora
- ¿Probabilidad de exactamente 3?

$$P(X=3) = \frac{e^{-5} \cdot 5^3}{3!} \approx \boxed{0.1404}$$

</v-clicks>

---
layout: intro
class: text-center
---

# PARTE II

## Distribuciones Continuas 📈

<div v-after class="text-sm opacity-75 mt-4">
Normal • Exponencial • Weibull
</div>

---
layout: text-image
media: 
---

# 5. Distribución Normal (Gaussiana) 🔔

<v-clicks depth="2">

- **Contexto**
  - Tiempo en landing page
  - Media: $\mu = 120$ segundos
  - Desviación estándar: $\sigma = 30$ segundos

- **Función de Densidad**
$$f(x) = \frac{1}{\sigma\sqrt{2\pi}} e^{-\frac{(x-\mu)^2}{2\sigma^2}}$$

- **Ejemplo Práctico**
  - ¿P(más de 150 segundos)?
  - Estandarización: $Z = \frac{150-120}{30} = 1$
  - $P(X > 150) = 1 - 0.8413 = \boxed{0.1587}$

</v-clicks>

---

# 6. Distribución Exponencial ⏱️

<div class="bg-green-50 p-4 rounded mb-4">
Modelo del tiempo entre eventos en procesos Poisson
</div>

<v-clicks>

### Relación con Poisson
- Si eventos siguen **Poisson** en el tiempo
- Los tiempos entre eventos son **Exponenciales**

### Fórmula de Supervivencia
$$P(X > x) = e^{-\lambda x}$$

### Caso Práctico
- Promedio: 1 conversión cada 12 minutos → $\lambda = \frac{1}{12}$
- ¿P(más de 20 minutos sin conversión)?

$$P(X > 20) = e^{-(1/12) \cdot 20} = e^{-1.667} \approx \boxed{0.1889}$$

</v-clicks>

---
layout: text-image
media: 
reverse: true
---

# 7. Distribución de Weibull 🌐

<v-clicks>

### Características
- Muy flexible para modelar tiempos
- Parámetros: forma $k$ y escala $\lambda$

### Casos Especiales
- Si $k = 1$ → Exponencial
- Si $k = 2$ → Rayleigh
- Si $k \approx 3.4$ → Similar a Normal

### Ejemplo
- Duración de sesión: $k=1.5$, $\lambda=100$ seg
- ¿P(sesión > 150 seg)?

$$P(X>150) = e^{-(150/100)^{1.5}} \approx \boxed{0.159}$$

</v-clicks>

---
zoom: 0.85
---

# Tabla Resumen: Distribuciones 📋

| Distribución | Tipo | Parámetros | Aplicación en Marketing Digital |
|-------------|------|------------|--------------------------------|
| **Bernoulli** | Discreta | $p$ | Clic vs. no clic en anuncio |
| **Binomial** | Discreta | $n, p$ | Número de clics en $n$ impresiones |
| **Multinomial** | Discreta | $n, p_1, ..., p_k$ | Tipos de interacción con anuncio |
| **Poisson** | Discreta | $\lambda$ | Conversiones por hora |
| **Normal** | Continua | $\mu, \sigma$ | Tiempo en página, ingresos/usuario |
| **Exponencial** | Continua | $\lambda$ | Tiempo entre eventos |
| **Weibull** | Continua | $k, \lambda$ | Duración sesiones, tiempo hasta fallo |

---
layout: center
---

# Análisis con Gráficos 📊

<div class="grid grid-cols-2 gap-6 mt-8">

<v-click at="1">
<div class="bg-blue-50 p-4 rounded">
<h3 class="font-bold text-blue-700">📊 Contraste Binomial</h3>
<p class="text-sm">Valida el CTR esperado (8%)</p>
<p class="text-xs opacity-75">Frecuencia de clics observada</p>
</div>
</v-click>

<v-click at="2">
<div class="bg-green-50 p-4 rounded">
<h3 class="font-bold text-green-700">📈 Tabla Multinomial</h3>
<p class="text-sm">Monitorea salud de campaña</p>
<p class="text-xs opacity-75">Click, view, spam_report</p>
</div>
</v-click>

<v-click at="3">
<div class="bg-purple-50 p-4 rounded">
<h3 class="font-bold text-purple-700">🔔 Histograma Normal</h3>
<p class="text-sm">Curva acampanada simétrica</p>
<p class="text-xs opacity-75">time_on_page con distribución Normal</p>
</div>
</v-click>

<v-click at="4">
<div class="bg-orange-50 p-4 rounded">
<h3 class="font-bold text-orange-700">⏳ Histograma Exponencial</h3>
<p class="text-sm">Forma de J invertida</p>
<p class="text-xs opacity-75">time_between_conversions</p>
</div>
</v-click>

</div>

---
layout: text-window
---

# Aplicaciones Administrativas 💼

<div v-motion
  :initial="{ opacity: 0, y: 20 }"
  :enter="{ opacity: 1, y: 0 }"
  class="text-lg mt-6">
Decisiones basadas en datos probabilísticos
</div>

::window::

╔════════════════════════════════════════╗
║  VALOR PARA LA AGENCIA DE MARKETING   ║
╠════════════════════════════════════════╣
║                                        ║
║  ✓ Predecir comportamientos            ║
║  ✓ Dimensionar recursos                ║
║  ✓ Optimizar presupuestos              ║
║  ✓ Establecer KPIs realistas           ║
║  ✓ Detectar anomalías                  ║
║  ✓ Planificar capacidad de servidores  ║
║  ✓ Mejorar targeting                   ║
║                                        ║
╚════════════════════════════════════════╝

---

# Conclusiones Clave 🎯

<v-clicks>

### 1️⃣ **Distribuciones Discretas**
Ideales para contar eventos: clics, conversiones, errores

### 2️⃣ **Distribuciones Continuas**
Modelan tiempos, duraciones, métricas continuas

### 3️⃣ **Relación Poisson-Exponencial**
- Eventos → Poisson
- Tiempos entre eventos → Exponencial

### 4️⃣ **Flexibilidad de Weibull**
La más versátil para modelar tiempos de vida y duraciones

### 5️⃣ **Decisiones Basadas en Datos**
Modelos probabilísticos rigurosos mejoran ROI

</v-clicks>

---
layout: intro
class: text-center
---

# ¡Gracias! 📊🚀

<div class="text-sm opacity-75 mt-8">
Distribuciones de Probabilidad aplicadas a Marketing Digital
</div>

<style>
.slidev-layout.intro {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}
.slidev-layout.intro h1, 
.slidev-layout.intro h2, 
.slidev-layout.intro h3,
.slidev-layout.intro div {
  color: white !important;
}
</style>