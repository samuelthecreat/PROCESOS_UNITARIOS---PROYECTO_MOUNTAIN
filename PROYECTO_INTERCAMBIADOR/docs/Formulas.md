# Fórmulas y Cálculos — Intercambiador y Transferencia en Paredes/Tuberías

**Notación y unidades (resumen)**

| Símbolo | Descripción | Unidad SI |
|---|---|---|
| $\dot{m}$ | Flujo másico | kg/s |
| $C_p$ | Capacidad calorífica específica | J/kg·K |
| $Q$ | Tasa de transferencia de calor | W |
| $U$ | Coeficiente global de transferencia | W/m²·K |
| $A$ | Área de intercambio | m² |
| $\Delta T_{lm}$ | Diferencia de temperatura media logarítmica | K |
| $\mathrm{NTU}$ | Número de unidades de transferencia | — |
| $C_r$ | Razón de capacidades térmicas $C_{min}/C_{max}$ | — |
| $k$ | Conductividad térmica del material | W/m·K |
| $L$ | Espesor de una capa de pared | m |
| $h$ | Coeficiente de convección superficial | W/m²·K |
| $R_f^{\prime\prime}$ | Factor de ensuciamiento (fouling) | m²·K/W |

---

## 1) Balance energético — fluido caliente (producto)

$$Q = \dot{m}_h \; C_{p,h} \; (T_{h,in} - T_{h,out})$$

Si $C_p$ está en kJ/kg·K multiplicar por 1000 para obtener $Q$ en W.

---

## 2) Flujo másico del fluido de servicio (agua)

$$\dot{m}_c = \frac{Q}{C_{p,c} \; (T_{c,out} - T_{c,in})}$$

---

## 3) Diferencia de temperatura media logarítmica (LMTD)

$$\Delta T_1 = T_{h,in} - T_{c,out} \qquad \Delta T_2 = T_{h,out} - T_{c,in}$$

$$\Delta T_{lm} = \frac{\Delta T_1 - \Delta T_2}{\ln\!\left(\dfrac{\Delta T_1}{\Delta T_2}\right)}$$

---

## 4) Relación general de transferencia de calor

$$Q = U \; A \; F \; \Delta T_{lm}$$

($F = 1$ para contracorriente ideal)

---

## 5) Área de transferencia requerida

$$A = \frac{Q}{U \; F \; \Delta T_{lm}}$$

---

## 6) Método NTU / Efectividad

$$C_{h} = \dot{m}_h C_{p,h},\quad C_{c} = \dot{m}_c C_{p,c}$$

$$C_{min} = \min(C_h,C_c),\quad C_r = \dfrac{C_{min}}{C_{max}}$$

$$\mathrm{NTU} = \dfrac{U\,A}{C_{min}}$$

Para contracorriente ($C_r\neq 1$):

$$\varepsilon = \frac{1 - e^{-\mathrm{NTU}(1-C_r)}}{1 - C_r\; e^{-\mathrm{NTU}(1-C_r)}}$$

$$Q = \varepsilon\; C_{min}\; (T_{h,in} - T_{c,in})$$

---

## 7) Ejemplo numérico (datos del proyecto)

**Datos de entrada:**
- Producto (yogur): $\dot{m}_h = 1.4\ \mathrm{kg/s}$, $C_{p,h} = 3.8\ \mathrm{kJ/kg\cdot K}$, $T_{h,in} = 45\ ^\circ\mathrm{C}$, $T_{h,out} = 6\ ^\circ\mathrm{C}$
- Agua de servicio: $C_{p,c} = 4.18\ \mathrm{kJ/kg\cdot K}$, $T_{c,in} = 2\ ^\circ\mathrm{C}$, $T_{c,out} = 14\ ^\circ\mathrm{C}$
- $U = 2500\ \mathrm{W/m^2\cdot K}$, $F = 1$

1) Carga térmica:

$$Q = 1.4 \times 3800 \times (45 - 6) = 207\,720\ \mathrm{W}$$

2) Flujo másico de agua:

$$\dot{m}_c = \frac{207\,720}{4180 \times 12} \approx 4.1426\ \mathrm{kg/s}$$

3) LMTD:

$$\Delta T_1 = 45 - 14 = 31\ \mathrm{K},\quad \Delta T_2 = 6 - 2 = 4\ \mathrm{K}$$

$$\Delta T_{lm} \approx 13.20\ \mathrm{K}$$

4) Área requerida:

$$A \approx 6.30\ \mathrm{m^2}$$

5) NTU/efectividad (verificación):

$$C_h = 1.4 \times 3800 = 5320\ \mathrm{W/K}$$

$$C_c = \dot{m}_c C_{p,c} = 4.1426 \times 4180 \approx 17310\ \mathrm{W/K}$$

$$C_r \approx 0.3073, \quad \mathrm{NTU} \approx 2.96, \quad \varepsilon \approx 0.907$$

---

## 8) Transferencia de calor a través de paredes, placas y tuberías

Estas secciones añaden las fórmulas para conducción en paredes planas y cilíndricas, y las correlaciones convectivas necesarias para un cálculo más realista.

### 8.1 Conducción en pared plana

$$Q = k\,A\,\frac{T_1 - T_2}{L}$$

$$R_{cond} = \frac{L}{k\,A}$$

Capas en serie (plana):

$$R_{total} = \sum_{i=1}^{n} \frac{L_i}{k_i\,A}$$

### 8.2 Conducción en pared cilíndrica (tubería)

Para una pared cilíndrica de longitud $L$ entre radios $r_1$ (interior) y $r_2$ (exterior):

$$Q = \frac{2\pi k L (T_{r_1} - T_{r_2})}{\ln(r_2/r_1)}$$

$$R_{cond,cil} = \frac{\ln(r_2/r_1)}{2\pi k L}$$

Las áreas de convección son $A_i = 2\pi r_i L$.

### 8.3 Resistencias convectivas y fouling

$$R_{conv} = \frac{1}{h\,A}$$

Fouling: $R_f = R_f^{\prime\prime}/A$.

### 8.4 Resistencia térmica total y coeficiente global $U$ (cilíndrico)

Resistencias en serie (interior → pared → exterior):

$$R_{total} = \frac{1}{h_i A_i} + \frac{\ln(r_2/r_1)}{2\pi k L} + \frac{1}{h_o A_o} + R_{f,i} + R_{f,o}$$

$$Q = \frac{T_{\infty,i} - T_{\infty,o}}{R_{total}} = U\,A_{ref}\,\Delta T_{lm}$$

$$\frac{1}{U} = \frac{R_{total}}{A_{ref}}$$

### 8.5 Coeficientes convectivos: Re, Pr, Nu y correlaciones

Reynolds: $Re = \dfrac{\rho V D}{\mu}$

Prandtl: $Pr = \dfrac{C_p \mu}{k}$

Nusselt: $Nu = \dfrac{h D}{k} \Rightarrow h = \dfrac{Nu\,k}{D}$

Correlaciones internas (tubería lisa):

- Re < 2300 (laminar, termo-desarrollado): $Nu = 3.66$ (pared isotérmica)
- Re > 10^4 (turbulento): Dittus–Boelter:

$$Nu = 0.023\; Re^{0.8}\; Pr^{n}, \quad n=0.4\ (calentamiento),\ n=0.3\ (enfriamiento)$$

- Gnielinski (2300 < Re < 5e6, 0.5 < Pr < 2000):

$$Nu = \frac{(f/8)(Re-1000)Pr}{1 + 12.7 (f/8)^{1/2} (Pr^{2/3}-1)}$$

Haaland para factor de fricción $f$:

$$\frac{1}{\sqrt{f}} = -1.8\log_{10}\left[ \left(\frac{\varepsilon/D}{3.7}\right)^{1.11} + \frac{6.9}{Re} \right]$$

### 8.6 Placas corrugadas y pasos de intercambiador

Usar datos del fabricante; en ausencia, modelar paso como canal y aplicar correlaciones internas con área hidráulica equivalente.

---

## 9) Plantilla Excel extendida (sugerida)

Entradas nuevas:
- `r_i`, `r_o`, `L`, `k_wall`, `h_i`, `h_o`, `rho`, `mu`, `Cp`, `k`, `epsilon`, `Rfi`, `Rfo`

Fórmulas ejemplo (Excel):
- `A_i` = `2*PI()*r_i*L`
- `A_o` = `2*PI()*r_o*L`
- `R_cond_cil` = `LN(r_o/r_i)/(2*PI()*k_wall*L)`
- `R_conv_i` = `1/(h_i*A_i)`
- `R_conv_o` = `1/(h_o*A_o)`
- `R_total` = `R_conv_i + R_cond_cil + R_conv_o + Rfi + Rfo`
- `U_ref` = `1/(R_total/A_o)`

---

## 10) Notas finales

- Incluir `R_f^{\prime\prime}` (ensuciamiento) para ambos lados.
- Para precisión en placas, usar datos del fabricante o CFD.
- ¿Deseas que genere el archivo `.xlsx` con estas hojas y fórmulas? Indica `sí` y lo creo.

## 8) Ley de Fourier — pared plana simple

Flujo de calor a través de una pared homogénea de espesor $L$, área $A$ y conductividad $k$:

$$Q = k\,A\,\frac{T_1 - T_2}{L}$$

Resistencia térmica de conducción equivalente (analógica a la resistencia eléctrica $R = V/I$):

$$R_{cond} = \frac{L}{k\,A} \qquad \Rightarrow \qquad Q = \frac{T_1 - T_2}{R_{cond}}$$

---

## 9) Pared compuesta en serie (capas de distintos materiales)

Cuando varias capas están apiladas una tras otra, las resistencias se suman (mismo flujo $Q$ atraviesa cada capa):

$$R_{total} = \sum_{i=1}^{n} \frac{L_i}{k_i\,A} = \frac{L_1}{k_1 A} + \frac{L_2}{k_2 A} + \cdots + \frac{L_n}{k_n A}$$

$$Q = \frac{T_{1} - T_{n+1}}{R_{total}}$$

Temperatura en la interfaz entre capas $i$ e $i+1$:

$$T_{i+1} = T_i - Q\,R_{cond,i}$$

---

## 10) Pared compuesta en serie con convección

Sistema completo: convección interior → pared multicapa → convección exterior. Las resistencias convectivas se añaden en los extremos:

$$R_{total} = \underbrace{\frac{1}{h_1 A}}_{\text{conv. int.}} + \sum_{i=1}^{n} \frac{L_i}{k_i A} + \underbrace{\frac{1}{h_2 A}}_{\text{conv. ext.}}$$

$$Q = \frac{T_{\infty,1} - T_{\infty,2}}{R_{total}}$$

---

## 11) Coeficiente global de transferencia $U$ — pared plana

$U$ resume todas las resistencias en serie por unidad de área, permitiendo escribir $Q = U A \Delta T$:

$$\frac{1}{U} = \frac{1}{h_1} + \frac{L_1}{k_1} + \frac{L_2}{k_2} + \cdots + \frac{L_n}{k_n} + \frac{1}{h_2}$$

---

## 12) Pared compuesta en paralelo

Cuando varias regiones de distinto material comparten la misma diferencia de temperatura $\Delta T$ (mismo área caliente/fría, pero materiales adyacentes), el calor total es la suma de cada camino:

$$Q_{total} = \frac{\Delta T}{R_A} + \frac{\Delta T}{R_B} + \cdots$$

Equivalente en resistencia paralela:

$$\frac{1}{R_{paralelo}} = \frac{1}{R_A} + \frac{1}{R_B} + \cdots$$

---

## 13) Pared compuesta mixta (serie–paralelo)

Arreglo donde alguna capa está formada por materiales en paralelo, mientras las demás capas están en serie. Se calcula la resistencia equivalente de la capa paralela y se suma en serie:

$$R_{eq,paralelo} = \frac{R_A\,R_B}{R_A + R_B}$$

$$R_{total} = R_{serie,1} + R_{eq,paralelo} + R_{serie,2} + \cdots$$

$$Q = \frac{\Delta T_{total}}{R_{total}}$$

---

## 14) Resistencia de ensuciamiento (fouling) en paredes

El depósito de incrustaciones aumenta la resistencia total. Se agrega una resistencia adicional $R_f = R_f^{\prime\prime}/A$ en cada superficie afectada:

$$R_{total} = \frac{1}{h_1 A} + \frac{R_{f,1}^{\prime\prime}}{A} + \sum_{i} \frac{L_i}{k_i A} + \frac{R_{f,2}^{\prime\prime}}{A} + \frac{1}{h_2 A}$$

$U$ con fouling a partir del $U$ limpio:

$$\frac{1}{U_f} = \frac{1}{U} + R_{f,1}^{\prime\prime} + R_{f,2}^{\prime\prime}$$

---

## 15) Conductividad térmica efectiva

Cuando un medio compuesto puede modelarse como un solo material equivalente:

**Capas en serie** (flujo perpendicular a las capas):

$$k_{ef} = \frac{L_{total}}{\displaystyle\sum_i \frac{L_i}{k_i}}$$

**Capas en paralelo** (flujo paralelo a las capas):

$$k_{ef} = \frac{\displaystyle\sum_i k_i\,A_i}{A_{total}}$$