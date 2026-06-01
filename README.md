# 🌆 Movilidad Urbana y Productividad Económica — LADB 2024

## 🧩 Contexto del negocio
Como analista en el American Development Bank, el objetivo es identificar en qué ciudades latinoamericanas conviene invertir en infraestructura de transporte para aumentar la productividad y el bienestar de la población.

## 🎯 Preguntas de negocio
1. ¿Qué ciudades presentan alta congestión y baja productividad?
2. ¿Cuáles muestran los mejores indicadores combinados?
3. ¿Qué variables tienen relación más fuerte con el desarrollo urbano?
4. ¿Existe correlación entre tiempo extra de viaje y contaminación PM2.5?
5. ¿Qué ciudades tienen mayor brecha entre tráfico histórico y en tiempo real, y cómo se correlaciona con el desempleo?

## 🛠️ Herramientas y librerías
- **Python** — pandas · numpy · seaborn · matplotlib
- **Jupyter Notebook** — documentación del pipeline completo
- **Fuentes de datos:** TomTom Traffic Index · OECD Cities

## 📂 Dataset
| Archivo | Descripción |
|---|---|
| `tomtom_traffic.csv` | 1,004,464 registros de congestión en tiempo real |
| `oecd_city_economy.csv` | PIB per cápita, desempleo, PM2.5 y población por ciudad |
| `ladb_mobility_economy_2024_clean.csv` | Dataset final limpio y unificado |

**Muestra final:** 15 ciudades · 7 países · año 2024

## 🔍 Pipeline de análisis
1. **Ingesta y EDA** — Carga, inspección estructural y detección de anomalías
2. **Limpieza y normalización** — snake_case, corrección de tipos, eliminación de caracteres regionales
3. **Segmentación temporal** — Filtrado al año 2024
4. **Agregación** — Promedios anuales por ciudad para compatibilizar frecuencias entre fuentes
5. **Integración** — Inner Join por `city` y `year`
6. **Visualización** — Boxplot, histograma, scatter plot y matriz de decisión bivariada
7. **Análisis extendido** — Correlación tráfico-PM2.5 y vulnerabilidad vial vs desempleo
8. **Exportación** — Dataset limpio en CSV

## 🚀 Análisis Extendido — Iniciativa Propia
Adicional a los entregables del proyecto, se plantearon y resolvieron 2 preguntas de negocio propias:

**Pregunta 4 — Tráfico y Calidad del Aire:**
¿Existe correlación entre el tiempo extra de viaje por tráfico (`mins_delay`) y los niveles de contaminación PM2.5?
→ Correlación positiva moderada de **0.64**, con São Paulo como anomalía que evidencia fuentes de contaminación independientes al tráfico vehicular.

**Pregunta 5 — Vulnerabilidad Vial y Mercado Laboral:**
¿Qué ciudades tienen mayor brecha entre tráfico histórico y tiempo real, y cómo se correlaciona con el desempleo?
→ Correlación negativa de **-0.59**; Bogotá emerge como caso atípico crítico confirmando congestión de carácter estructural 
independiente del ciclo económico.

## 💡 Hallazgos principales
- **Sin correlación lineal PIB-tráfico:** La riqueza económica no predice el nivel de congestión, rompiendo el supuesto tradicional
- **Ciudad de México** lidera la congestión global con 2,833 min de retraso promedio, superando a Tokio y Nueva York
- **Montevideo** es el modelo de eficiencia: PIB más alto de la muestra con el retraso vial más bajo
- **Bogotá y Lima** presentan alta congestión con PIB moderado-bajo, indicando déficit estructural en transporte masivo
- **Correlación tráfico-PM2.5:** 0.64 — relación positiva moderada; São Paulo es anomalía con contaminación alta y retraso medio
- **Vulnerabilidad vial vs desempleo:** Correlación negativa (-0.59); Bogotá confirma congestión estructural independiente del ciclo económico

## 🎯 Recomendaciones de inversión
1. **Prioridad 1 — Bogotá:** Mayor retorno marginal por desbloqueo de movilidad estructural
2. **Prioridad 2 — Santiago:** PIB más bajo con congestión moderada-alta
3. **Fase II recomendada:** Cruzar PM2.5 y densidad poblacional antes de aprobar vehículos financieros

## 📁 Archivos del repositorio
- `Movilidad_urbana_y_productividad_económica.ipynb` — Pipeline completo
- `Movilidad_urbana_y_productividad_económica.pdf` — Versión exportada
- `ladb_mobility_economy_2024_clean.csv` — Dataset final de producción






