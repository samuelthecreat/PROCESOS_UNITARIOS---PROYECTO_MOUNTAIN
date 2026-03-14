# Diseño Térmico de Intercambiador de Placas para Enfriamiento de Yogur Líquido

## 1. Introducción y Objetivo del Diseño

El presente documento detalla el dimensionamiento térmico y mecánico de un intercambiador de calor de placas (PHE, *Plate Heat Exchanger*) destinado al enfriamiento de yogur líquido comercial en una operación industrial de régimen permanente.

El objetivo principal es reducir la temperatura de 1.4 kg/s de yogur desde 45 °C (temperatura de salida de la pasteurización) hasta 6 °C (temperatura de envasado y almacenamiento seguro), extrayendo una carga térmica de 207.48 kW mediante agua helada en arreglo contracorriente.

Dado que el yogur es una suspensión coloidal con estructura proteica delicada, el diseño prioriza un enfriamiento suave que evite altos esfuerzos de corte para preservar la textura, viscosidad y calidad organoléptica del producto final.

## 2. Datos de Operación y Parámetros Generales

| Parámetro | Valor de Diseño |
| :--- | :--- |
| **Calor Total a Transferir ($Q$)** | 207.48 kW |
| **Diferencia de Temperatura Media Logarítmica ($\Delta T_{LMTD}$)** | 13.15 K |
| **Fluido Caliente (Producto)** | Yogur Líquido Comercial |
| **Caudal Másico de Yogur** | 1.4 kg/s |
| **Temperaturas del Yogur (Entrada / Salida)** | 45 °C / 6 °C |
| **Fluido Frío (Servicio)** | Agua Helada |
| **Caudal Másico de Agua** | 4.14 kg/s |
| **Tipo de Intercambiador** | Intercambiador de Placas Corrugadas (PHE) |
| **Arreglo de Flujo** | Contracorriente, Múltiples Pasos |

---

## 3. Análisis Térmico y Criterios de Transferencia de Calor

### 3.1 Comportamiento Reológico del Yogur

El yogur líquido comercial es un fluido no-newtoniano de tipo pseudoplástico (shear-thinning) con viscosidad aparente significativa. Esta característica reológica determina el régimen de flujo dentro del intercambiador, siendo predominantemente laminar o de transición incluso a velocidades moderadas.

Para el dimensionamiento, se evaluaron dos escenarios termodinámicos:

**Escenario Teórico:** Un cálculo preliminar asumiendo un coeficiente global ($U$) idealizado de 2.5 kW/m²K sugería un área de transferencia de 6.3 m². Sin embargo, este escenario presupone un régimen de flujo altamente turbulento, típico de fluidos de baja viscosidad como agua o leche cruda, siendo mecánicamente inviable para el yogur.

**Escenario Real (Modelo Adoptado):** El análisis de resistencias térmicas determinó que el coeficiente convectivo del yogur, limitado por su viscosidad aparente, actúa como el factor restrictivo (cuello de botella térmico) del sistema. Forzar mayores coeficientes convectivos requeriría velocidades de flujo extremas que causarían alto esfuerzo cortante, destruyendo la estructura proteica.

### 3.2 Coeficientes de Transferencia de Calor

| Parámetro Térmico | Valor Calculado |
| :--- | :--- |
| **Coeficiente Convectivo del Agua ($h_{agua}$)** | 3.1174 kW/m²K |
| **Coeficiente Convectivo del Yogur ($h_{yogur}$)** | 0.4576 kW/m²K *(Factor limitante)* |
| **Conductividad Térmica de la Placa ($k_{placa}$)** | 0.015 kW/mK (Acero Inoxidable) |
| **Espesor de Placa ($e$)** | 0.5 mm (0.0005 m) |
| **Coeficiente Global de Diseño ($U$)** | **0.3938 kW/m²K** |

**Análisis de Resistencias:**

La ecuación de resistencias en serie es:
$$\frac{1}{U} = \frac{1}{h_{yogur}} + \frac{e}{k_{placa}} + \frac{1}{h_{agua}}$$

Desglose porcentual de resistencias totales:
- Resistencia del Yogur: 85.3%
- Resistencia de la Placa: 1.3% (despreciable)
- Resistencia del Agua: 13.4%

La dominancia de la resistencia del yogur confirma que su comportamiento reológico es el parámetro crítico de diseño.

### 3.3 Justificación de Área Ampliada

La limitación térmica natural del fluido requiere compensación mediante aumento de área superficial. Mantener el coeficiente convectivo del yogur a su valor calculado ($h = 0.462$ kW/m²K), sin alcanzar velocidades destructivas, conduce a:

$$A = \frac{Q}{U \cdot \Delta T_{LMTD}} = \frac{207.48}{0.394 \times 13.15} = 40.0 \text{ m}^2$$

Este área se distribuye en un arreglo optimizado de placas bajo configuración multipaso, garantizando mantener la velocidad y los coeficientes calculados en cada paso.

---

## 4. Configuración Multipaso del Intercambiador

Para evitar la caída de velocidad y la consecuente reducción de coeficientes convectivos cuando se utilizan múltiples placas, se implementa una **configuración de 6 pasos**. Esta solución permite mantener los parámetros térmicos calculados sin recalcular el diseño.

### 4.1 Distribución de Canales

| Parámetro | Valor |
| :--- | :--- |
| **Canales por Paso (Yogur)** | 13 canales |
| **Canales por Paso (Agua)** | 13 canales |
| **Número de Pasos** | 6 pasos |
| **Total Canales Térmicos (Yogur)** | 78 canales |
| **Total Canales Térmicos (Agua)** | 78 canales |
| **Placas Térmicas Totales** | 156 placas |
| **Área Total Instalada** | 39.0 m² |

### 4.2 Funcionamiento del Arreglo Multipaso

En cada paso, el fluido entra y circula por 13 canales paralelos, manteniendo la velocidad de diseño original. Al llegar al final de la sección, choca contra una placa ciega y da la vuelta hacia el siguiente conjunto de 13 canales. Este proceso se repite 6 veces, recorriendo una distancia total equivalente a 6 traversías de la longitud de placa.

---

## 5. Especificaciones Físicas del Equipo

| Especificación | Detalle |
| :--- | :--- |
| **Área Total Requerida de Transferencia** | 39.0 m² |
| **Área Individual por Placa** | 0.25 m² |
| **Dimensiones de la Placa** | 0.4 m (ancho) × 0.625 m (largo útil) |
| **Espesor de Placa** | 0.5 mm (0.0005 m) |
| **Separación entre Placas (Espaciamiento de Canal)** | 4 mm |
| **Número Total de Placas** | 156 placas |
| **Material de Placas** | Acero Inoxidable AISI 316 |
| **Tipo de Corrugación** | Corrugación Chevron (ángulo óptimo para régimen laminar) |

---

## 6. Análisis Hidráulico y Caída de Presión

El dimensionamiento basado en una mayor cantidad de placas distribuidas en múltiples pasos genera una ventaja hidráulica crítica: mantiene baja la velocidad en cada canal, resultando en pérdidas de carga mínimas.

### 6.1 Pérdida de Carga Lado Yogur

En un solo paso a velocidad de diseño (0.064 m/s), usando la ecuación de Darcy-Weisbach:
- Caída de presión por paso: 2.02 kPa
- Seis traversías: $2.02 \times 6 = 12.12$ kPa
- Pérdidas menores en giros (5 retornos en "U"): ~2-3 kPa
- **Caída Total: ~14.5 kPa (0.145 bar)**

### 6.2 Pérdida de Carga Lado Agua

El agua, siendo 100 veces menos viscosa que el yogur, fluye con resistencia mínima:
- Caída de presión en 6 pasos: ~1-2 kPa (0.02 bar)

### 6.3 Implicaciones Operativas

Estos valores garantizan:
1. **Ahorro energético:** Requiere bombas de baja presión (2-4 bar), minimizando consumo eléctrico.
2. **Protección del producto:** Bajo esfuerzo cortante confirma que la estructura proteica del yogur no sufre degradación mecánica.
3. **Integridad del equipo:** Presiones lejanas a los límites de resistencia de los empaques (10-15 bar), eliminando riesgo de fugas por sobrepresión.

---

## 7. Configuración de Flujo y Operación

### 7.1 Arranjo Contracorriente

El intercambiador operará en configuración de flujo en **contracorriente**, maximizando la diferencia de temperatura media logarítmica a lo largo de toda la superficie de intercambio. Este arranjo es termodinámicamente superior al flujo paralelo para este tipo de equipos.

### 7.2 Mantenimiento e Inocuidad (CIP)

La configuración multipaso con todas las conexiones ubicadas en el cabezal fijo permite:
- Desmontaje sin desconectar tuberías de la planta
- Inspecciones visuales de placas y empaques
- Ciclos de Limpieza en Sitio (CIP - *Cleaning In Place*) por circulación de soluciones sanitarias
- Cumplimiento con estándares ASME BPE para equipos de alimentos

---

## 8. Análisis de Costos de Inversión y Operación (CAPEX y OPEX)

El siguiente análisis refleja estimaciones realistas para el mercado industrial de **Santa Cruz, Bolivia** (referencias de tarifas locales de SAGUAPAC y CRE), enfocado específicamente en los componentes del sistema de enfriamiento (intercambiador y bombeo asociado).

### 8.1 CAPEX (Inversión de Capital)

El costo de los equipos incluye montos de importación (aprox. 30%-40% sobre el valor FOB para ingresar a Bolivia) para equipos de acero inoxidable sanitario que generalmente provienen de Brasil, Europa o Asia.

| Componente (Especificación) | Costo Estimado (USD) | Costo Estimado (Bs) |
| :--- | :--- | :--- |
| **PHE AISI 316 (39 m², 156 placas)**<br>*Empaques EPDM grado alimentario, bastidor* | $12,000 – $18,000 | 83,500 – 125,200 |
| **Bomba Sanitaria para Yogur**<br>*Centrífuga higiénica o lóbulo, ~1.4 kg/s (5 m³/h)* | $2,500 – $4,000 | 17,400 – 27,800 |
| **Bomba de Agua Helada**<br>*Centrífuga estándar, ~4.14 kg/s (15 m³/h)* | $800 – $1,500 | 5,500 – 10,400 |
| **Accesorios y Tuberías**<br>*Válvulas higiénicas, flujómetros, tubería AISI 316* | $1,500 – $3,000 | 10,400 – 20,800 |
| **Inversión Total Estimada (Equipos)** | **$16,800 – $26,500** | **116,800 – 184,200** |

*(Nota: Esta estimación excluye el equipo generador de agua helada o Chiller, el cual representa una inversión separada).*

### 8.2 OPEX (Costos Operativos Mensuales)

Se asume un régimen de operación industrial estándar de **8 horas diarias por 26 días al mes (208 horas/mes)**.

#### 8.2.1 Consumo Eléctrico (CRE - Cooperativa Rural de Electrificación)

Para la categoría Industrial (Grandes Consumidores en Santa Cruz), la tarifa promedia los **$0.06 USD/kWh (aprox. 0.42 Bs/kWh)**.
*   **Potencia Instalada (Bombeo):** Bomba de yogur (~3 kW) + Bomba de agua helada (~2 kW) = 5 kW.
*   **Consumo Mensual:** 5 kW × 208 h/mes = 1,040 kWh/mes.
*   **Costo Eléctrico Mensual (Bombeo):** 1,040 kWh × $0.06 = **$62.40 USD/mes (aprox. 437 Bs/mes)**.

#### 8.2.2 Consumo de Agua (SAGUAPAC)

El agua en este sistema se utiliza como fluido de servicio en circuito cerrado (reposición) y para ciclos de limpieza (CIP).
*   **Tarifa Industrial SAGUAPAC:** ~$0.35 USD/m³ (2.45 Bs/m³). Con el recargo de alcantarillado (aprox. 100%), el costo real es cercano a **$0.70 USD/m³ (4.90 Bs/m³)**.
*   **Consumo Mensual Estimado:** Reposición de agua helada y ciclos de limpieza (CIP) = ~40 m³/mes.
*   **Costo de Agua Mensual:** 40 m³ × $0.70 = **$28 USD/mes (aprox. 196 Bs/mes)**.

#### 8.2.3 Resumen de OPEX Directo (PHE y Bombeo)

| Concepto | Costo Mensual (USD) | Costo Mensual (Bs) |
| :--- | :--- | :--- |
| **Energía Eléctrica (CRE)** | $62.40 | 437 |
| **Agua Potable y Alcantarillado (SAGUAPAC)** | $28 | 196 |
| **Total Operativo Directo** | **$90.40 / mes** | **633 / mes** |

---

### 8.2.4 Escenarios de Operación y Comparación

Para evaluar la escala de producción y su impacto en OPEX, se proponen cuatro escenarios representativos. Se asume tarifa eléctrica de **$0.06 USD/kWh** y costo de agua + alcantarillado conservado en **$0.70 USD/m³** (40 m³/mes → $28/mes). Potencia de bombeo considerada: **5 kW**.

| Escenario | Horas/mes | Energía (kWh/mes) | Costo Energía (USD) | Costo Agua (USD) | Total OPEX (USD/mes) | Total OPEX (Bs/mes, 7 Bs/USD) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Base (actual) | 208 h | 1,040 | $62.40 | $28 | **$90.40** | **633** |
| Turno medio | 360 h | 1,800 | $108.00 | $28 | **$136.00** | **952** |
| Producción extendida | 480 h | 2,400 | $144.00 | $28 | **$172.00** | **1,204** |
| Operación continua | 720 h | 3,600 | $216.00 | $28 | **$244.00** | **1,708** |

**Notas:**
- Los costos en Bolivianos usan un tipo de cambio aproximado de **7 Bs / 1 USD** para consistencia con secciones previas.
- El consumo de agua se mantiene constante por mes asumiendo mismas necesidades de reposición y CIP; si cambian ciclos CIP o reposición, ajustar el valor de m³/mes.

Se recomienda presentar al menos dos escenarios en cualquier presupuesto: un escenario operativo realista (p. ej. 480 h/mes para plantas en turno extendido) y un escenario conservador/peaking (720 h/mes) para evaluar sensibilidad de costos.

## 9. Supuestos y Consideraciones de Diseño

### 9.1 Condiciones Adiabáticas en Conexiones

Para el balance de energía y dimensionamiento del equipo, se asume que el intercambiador de calor y sus tuberías de conexión operan bajo condiciones adiabáticas respecto al ambiente.

Aunque existe transferencia de calor por conducción en paredes cilíndricas y convección hacia el aire ambiente, este valor es matemáticamente despreciable (<1% del total) debido a:
1. **Área superficial mínima:** La tubería de conexión representa una fracción insignificante comparada con los 39 m² de placas.
2. **Tiempo de residencia:** El fluido permanece en tramos externos apenas unos segundos, insuficiente para intercambio térmico significativo.
3. **Aislamiento térmico:** La línea de salida de yogur a 6 °C incluye recubrimiento elastomérico que corta la transferencia calorífica con el ambiente.

### 9.2 Propiedades Constantes

Se asumen propiedades térmicas y reológicas constantes del yogur en el rango 45-6 °C. Para refinos futuros, puede considerarse variación lineal de $\mu(T)$ si se requiere mayor precisión.

### 9.3 Régimen Permanente

El diseño corresponde a operación continua sin acumulación de energía ni fluctuaciones transitorias en caudales o temperaturas.

---

## 10. Validación y Verificación

El diseño obtenido mediante el método LMTD ha sido coordinado con criterios fisiológicos del fluido de trabajo y factibilidad hidráulica, resultando en un equipo técnicamente viable, económicamente accesible y operativamente robusto para su implementación industrial.


