# 🌦️ Dashboard Clima Uruguay

![Status](https://img.shields.io/badge/Status-Active-success)
![License](https://img.shields.io/badge/License-MIT-blue)
![Tech](https://img.shields.io/badge/Stack-HTML5%20|%20Bootstrap%205%20|%20JS-orange)

Un dashboard meteorológico moderno y responsivo diseñado para monitorear las condiciones climáticas en tiempo real en la costa de Uruguay (específicamente **Solymar** y **Montevideo**).

El sistema integra datos de múltiples fuentes (Open-Meteo, Windy, Windguru) para ofrecer una visión completa: desde alertas de lluvia inminente hasta mapas sinópticos de viento.

Se puede ver un ejemplo funcional en https://morkx.github.io/clima-uruguay/

---

## 🚀 Características Principales

### 1. Sistema de Alerta Temprana (Lluvia)
- **Análisis en tiempo real:** El sistema consulta la API cada vez que se carga la página.
- **Lógica de Alerta:** Analiza las próximas **2 horas**. Si la probabilidad de precipitación supera el **50%** o se detecta una acumulación > 0.1mm, despliega una alerta visual roja en el encabezado.

### 2. Visualización de Datos (Chart.js)
- Gráfico combinado de **Temperatura** (línea spline suavizada) y **Probabilidad de Lluvia** (barras).
- Eje temporal dinámico sincronizado con la hora actual del usuario.
- Proyección de datos a 48 horas.

### 3. Integración de APIs y Widgets
- **Open-Meteo API:** Datos crudos para temperatura, humedad, presión, UV y lluvia.
- **Windy & Windguru:** Embeds (iframes) para mapas de viento y tablas de mareas/surf.
- **Filtrado Dinámico:** Permite alternar la vista entre "Solymar", "Montevideo" o "Todos" sin recargar la página.

---

## 🛠️ Tecnologías Utilizadas

* **Core:** HTML5, CSS3, JavaScript (ES6).
* **Framework CSS:** [Bootstrap 5.3](https://getbootstrap.com/) (Diseño Dark/Light híbrido).
* **Gráficos:** [Chart.js](https://www.chartjs.org/).
* **Fuente de Datos:** [Open-Meteo API](https://open-meteo.com/) (Sin necesidad de API Key).
* **Iconografía:** FontAwesome 6.

---

## 📦 Instalación y Uso

Este proyecto es una aplicación estática (Static Web App), por lo que no requiere backend ni compilación.

1.  **Clonar el repositorio:**
    ```bash
    git clone https://github.com/morkx/clima-uruguay.git
    cd clima-uruguay
    ```

2.  **Ejecutar:**
    Simplemente abre el archivo `index.html` en tu navegador favorito.
    
    *Opción recomendada (para evitar problemas de CORS locales):*
    ```bash
    # Si tienes Python instalado
    python -m http.server 8000
    # Luego abre http://localhost:8000
    ```

---

## ⚙️ Configuración

Las coordenadas por defecto están configuradas para la zona de **Ciudad de la Costa (-34.82, -55.95)**.

Para modificar la ubicación de la API principal, edita la variable `apiUrl` en `index.html`:

```javascript
const apiUrl = "https://api.open-meteo.com/v1/forecast?latitude=TU_LATITUD&longitude=TU_LONGITUD&...";
```