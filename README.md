# An-lisis-de-Marketing-y-LTV-Showz-Estudio-de-Caso-
Análisis del comportamiento de usuarios y métricas de marketing para optimizar inversiones publicitarias: cohortes, embudo de conversión, CAC y LTV usando datos de visitas, pedidos y costos.

## 📋 Descripción breve
Análisis de comportamiento de usuarios y rentabilidad de campañas para Showz, una plataforma de venta de entradas. Se estudian visitas, pedidos y gastos de marketing (2017–2018) para calcular métricas clave (CAC, LTV, ROMI), analizar cohorts y optimizar la asignación de presupuesto.

---

## 🎯 Objetivos
- Entender cómo usan los clientes el servicio y cuándo convierten (tiempo hasta la primera compra).  
- Medir cuánto aporta cada cliente en ingresos (LTV) y cuándo se recupera el costo de adquisición (CAC → payback).  
- Evaluar la rentabilidad por canal/fuente (ROMI) y recomendar dónde invertir de manera óptima.  
- Visualizar embudos, cohorts y proponer decisiones accionables para marketing.

---

## 📂 Datasets (rutas en repo)
- `datasets/visits_log_us.csv` — logs de sesiones (Uid, Device, Start Ts, End Ts, Source Id)  
- `datasets/orders_log_us.csv` — pedidos (Uid, Buy Ts, Revenue)  
- `datasets/costs_us.csv` — gastos de marketing por fuente y fecha (source_id, dt, costs)

---

## 🔎 Metodología / Flujo de trabajo
1. **Carga y limpieza de datos**
   - Renombrar columnas, parseo de timestamps, comprobación de nulls, tipos correctos.
   - Crear columnas útiles: `date`, `session_length`, `cohort`, `days_to_first_purchase`, etc.
2. **Análisis descriptivo**
   - Eventos: usuarios totales, sesiones diarias/semanales/mensuales, duración de sesiones, recurrencia.
3. **Análisis de conversión y cohorts**
   - Calcular cohortes por fecha de primera visita/registro y medir la tasa de conversión por cohorte a lo largo del tiempo.
   - Medir qué porcentaje de usuarios completa TODO el embudo hasta la compra.
4. **Cálculo de LTV y CAC**
   - LTV: ingresos por usuario acumulados por ventana temporal (30/60/90/365 días según enfoque).
   - CAC: costos totales por fuente / nuevos clientes de esa fuente en el periodo.
   - Payback: tiempo hasta que LTV acumulado ≥ CAC.
5. **Análisis de ROMI**
   - ROMI = (Ingresos atribuibles al canal − Costos del canal) / Costos del canal
6. **Recomendaciones**
   - Priorizar canales con CAC bajo y LTV alto; proponer redistribución de presupuesto.

---

## 📊 Métricas clave a calcular e interpretar
- **Usuarios activos diarios / semanales / mensuales (DAU/WAU/MAU)**  
- **Sesiones por usuario y duración media de sesión**  
- **Tasa de retención por cohorte** (D+0, D+7, D+30, etc.)  
- **Tasa de conversión (visit → compra)** por fuente y cohorte  
- **LTV (D30, D90, D365 según alcance)** — ingreso medio por usuario en ventanas temporales  
- **CAC por fuente** — costo de adquisición por nuevo cliente por canal  
- **ROMI por fuente** — rentabilidad de la inversión publicitaria  
- **Payback period** — días hasta recuperar CAC

---

## 🗂 Estructura del repositorio

- README.md
- visits_log_us.csv
- orders_log_us.csv
- costs_us.csv
- sprint9_showz_marketing.ipynb
