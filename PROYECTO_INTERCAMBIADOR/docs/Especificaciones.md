# Especificaciones del Proyecto - Intercambiador de Calor

## 1. Descripción General

Este documento detalla las especificaciones técnicas y funcionales del proyecto de diseño térmico de un intercambiador de calor para la industria láctea, específicamente para el enfriamiento de yogur líquido. Incluye los requisitos del sistema, parámetros de operación y criterios de diseño, sirviendo como guía para el desarrollo e implementación.

---

## 2. Información General del Sistema

| Parámetro                  | Valor           |
|---------------------------|-----------------|
| **Producto**              | Yogur Líquido   |
| **Proceso**               | Enfriamiento    |
| **Tipo de Intercambiador**| Placas          |
| **Arreglo de Flujo**      | Contracorriente |

---

## 3. Especificaciones de los Fluidos

### 3.1. Producto (Fluido Caliente)

| Parámetro                | Valor | Unidad     |
|--------------------------|-------|------------|
| Fluido                   | Yogur Líquido | -      |
| Flujo másico             | 1.4   | kg/s       |
| Capacidad calorífica (Cp)| 3.8   | kJ/kg·K    |
| Temperatura entrada      | 45    | °C         |
| Temperatura salida       | 6     | °C         |

### 3.2. Fluido de Servicio (Frío)

| Parámetro                | Valor | Unidad     |
|--------------------------|-------|------------|
| Fluido                   | Agua  | -          |
| Capacidad calorífica (Cp)| 4.18  | kJ/kg·K    |
| Temperatura entrada      | 2     | °C         |
| Temperatura salida       | 14    | °C         |

---

## 4. Parámetros de Diseño

| Parámetro                                         | Valor  | Unidad    |
|---------------------------------------------------|--------|-----------|
| Coeficiente global de transferencia de calor (U)  | 2500   | W/m²·K    |

---

## 5. Cálculos Preliminares

### 5.1. Carga térmica del proceso

- ΔT (Yogur) = 45 - 6 = 39°C
- Q = ṁ × Cp × ΔT = 1.4 × 3.8 × 39 = 207.72 kW

### 5.2. Flujo másico de agua requerido

- ΔT (Agua) = 14 - 2 = 12°C
- ṁ agua = Q / (Cp × ΔT) = 207.72 / (4.18 × 12) = 4.14 kg/s

---

## 6. Consideraciones de Diseño

- **Área de placas comerciales:** 0.20 m², 0.25 m², 0.30 m² por placa.
- **Longitudes comerciales de tubos:** 3 m o 3.6 m (común en lácteos).
- **Diámetro estándar de tubos:** 19.05 mm.
- **Diámetro de la coraza:** 200 mm a 300 mm.
- El sistema operará en régimen permanente, sin acumulación de energía y con propiedades térmicas constantes.
- Se deben considerar condiciones sanitarias propias de la industria alimentaria.

---

## 7. Objetivos del Proyecto

### General

Diseñar térmicamente un intercambiador de calor para un proceso de la industria láctea, aplicando principios de transferencia de calor, balances de energía y criterios de ingeniería, para alcanzar las condiciones operativas requeridas.

### Específicos

- Identificar y describir el proceso térmico asignado.
- Seleccionar y justificar el tipo de intercambiador de calor.
- Realizar el balance de energía del sistema en régimen permanente.
- Calcular la carga térmica requerida.
- Determinar la diferencia media logarítmica de temperaturas (LMTD).
- Estimar el coeficiente global de transferencia de calor.
- Calcular el área de transferencia de calor necesaria.
- Analizar la factibilidad técnica del diseño obtenido.

---

## 8. Alcance del Proyecto

El proyecto se limita al diseño térmico del intercambiador de calor. No incluye cálculos mecánicos detallados, diseño estructural, selección comercial de fabricante ni análisis económico profundo, aunque se valorará la discusión técnica relacionada.

---

## 9. Actividades a Desarrollar

1. Descripción del proceso industrial asignado.
2. Selección y justificación del tipo de intercambiador de calor.
3. Definición de datos de operación y supuestos de diseño.
4. Desarrollo del balance de energía.
5. Cálculo de la carga térmica del proceso.
6. Determinación de la diferencia media logarítmica de temperaturas.
7. Selección de un valor adecuado del coeficiente global de transferencia de calor.
8. Cálculo del área requerida de transferencia de calor.
9. Resolución mediante el método LMTD y verificación con el método NTU–ε.
10. Elaboración del informe técnico con cálculos, tablas, resultados y esquemas.

---

## 10. Criterios de Evaluación

- Aplicación correcta de los principios de transferencia de calor.
- Coherencia y claridad en los cálculos.
- Justificación técnica de las decisiones de diseño.
- Presentación, orden y redacción técnica del informe.
- Capacidad de análisis e interpretación de resultados.

