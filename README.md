# 📊 Observatorio Turístico Delicias - Dashboard Interactivo

Un panel de inteligencia de negocios interactivo y profesional diseñado para monitorear, analizar y proyectar el crecimiento turístico y económico en la región de Delicias, Chihuahua (Corredor Perlas del Conchos).

**Diseñado, desarrollado e integrado por: Alonso Villalobos** 🚀

---

## 🎯 Descripción del Proyecto

Este proyecto nace de la necesidad de unificar, visualizar y entender los datos turísticos de la región de Delicias. A través de este tablero, es posible evaluar el impacto de eventos culturales, deportivos y agroindustriales, así como visualizar métricas macroeconómicas fundamentales como la ocupación hotelera, la derrama económica y la participación estatal.

El panel se divide en dos secciones estratégicas:
1. **Monitoreo de Eventos:** Análisis de afluencia, ocupación y correlación de gasto vs. estancia según el tipo de evento (2022-2026).
2. **Impacto Regional y Macroeconómico:** Visión panorámica del crecimiento económico de Delicias, proyectos de infraestructura y políticas públicas (Ley de Turismo).

---

## 🛠️ Tecnologías Utilizadas

Para garantizar una implementación rápida, ligera y sin necesidad de configurar servidores o entornos de desarrollo complejos (como Node.js o Webpack), estructuré este proyecto para que funcione directamente en el navegador utilizando **CDNs**:

* **React 18 & ReactDOM:** Para la construcción de la interfaz de usuario basada en componentes y manejo de estados.
* **Tailwind CSS:** Para un diseño moderno, responsivo y un estilizado ágil directamente en las clases de HTML.
* **Recharts:** Librería de gráficos basada en D3.js y React para los histogramas, gráficas de área, dispersión y barras.
* **Babel (Standalone):** Para compilar código JSX en tiempo real dentro del navegador.
* **Lucide React:** Para la iconografía temática y profesional.

---

## 🛤️ Proceso de Integración paso a paso (Por Alonso Villalobos)

A continuación, detallo el proceso lógico y técnico que llevé a cabo para construir este tablero desde cero:

### 1. Análisis y Estructuración de Datos
* **Recopilación:** Tomé los datos crudos provistos en diferentes archivos CSV y Excel sobre eventos turísticos (fechas, asistentes, tipos) y métricas macroeconómicas (derrama, pernoctas, registros nacionales).
* **Limpieza y Unificación:** Transformé estos datos en una estructura JSON plana y coherente que pudiera ser consumida fácilmente por los componentes de React, proyectando datos históricos desde 2022 y estimaciones hasta 2026.

### 2. Diseño de la Experiencia de Usuario (UX) y la Interfaz (UI)
* **Paleta de Colores:** Definí una paleta inspirada en la región: tonos nogal (ámbar), agricultura (esmeralda), desierto y atardeceres.
* **Tooltips Estratégicos:** Programé un componente interactivo (el icono de "foco") para que cada gráfica y tarjeta no solo mostrara números, sino que explicara **para qué sirve el dato y qué estrategia gubernamental o comercial implementar**.

### 3. Desarrollo de Componentes Lógicos (React)
* **Tarjetas KPI dinámicas:** Componentes reutilizables que calculan automáticamente los totales y promedios según el filtro de año seleccionado.
* **Navegación por Pestañas (Tabs):** Implementé estados (`useState`) para alternar entre el análisis pormenorizado de eventos y la vista macroeconómica sin recargar la página.
* **Filtros Inteligentes:** Extraje los años disponibles dinámicamente (`useMemo`) para generar botones de filtrado que actualizan todas las gráficas en tiempo real.

### 4. Visualización Avanzada de Datos (Recharts)
Integré múltiples tipos de gráficos para contar la historia detrás de los datos:
* **Gráficas de Área:** Para identificar la estacionalidad (meses pico y meses valle).
* **Gráficas de Dispersión (Scatter):** Para demostrar correlaciones complejas, como qué tipo de eventos (ej. Agroindustria vs. Deporte) generan mayor retención (días de estancia) y mejor monetización (gasto promedio).
* **Gráficas Compuestas:** Para cruzar barras de derrama económica con líneas de porcentaje de participación estatal.

### 5. Arquitectura "Zero-Build" (Todo en un archivo)
* Para facilitar el despliegue y la adopción, condensé todo el código React, el CSS y los datos dentro de un único archivo `index.html`. 
* Resolví problemas de compatibilidad de dependencias (como el error de `ForwardRef` en Recharts) fijando versiones estables en los scripts del `<head>`.

---

## 🚀 Cómo desplegar y usar el proyecto

Al estar diseñado como una arquitectura estática (Single-File App), el despliegue es inmediato:

1. **Uso local:** Simplemente haz doble clic en el archivo `index.html` y se abrirá en cualquier navegador web moderno. ¡Ya está funcionando!
   
2. **Despliegue en GitHub Pages (Gratis):**
   * Crea un nuevo repositorio en GitHub.
   * Sube el archivo `index.html` a la rama `main`.
   * Ve a **Settings > Pages**.
   * En "Source", selecciona `Deploy from a branch`, elige `main` y guarda.
   * En un par de minutos, tendrás un enlace público con el tablero funcional.

---

## 🔄 Futuras Actualizaciones de Datos

Actualmente, los datos están integrados dentro de la función `getDeliciasEventData()` en el archivo HTML. 

Si en el futuro deseas conectar este tablero a una hoja de Google Sheets en tiempo real:
1. Sube tu base de datos a Google Sheets.
2. Publica la hoja en formato CSV (`Archivo > Compartir > Publicar en la Web`).
3. Reemplaza la carga estática en el `useEffect` por una llamada `fetch('URL_DE_TU_CSV')` y parsea los resultados.

---
*Documentación creada por Alonso Villalobos.*
