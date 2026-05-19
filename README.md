# 📦 Proyecto de Análisis Supply Chain

**Nota:** Los datos utilizados son ficticios, creados ad hoc para este proyecto con fines académicos.

---

## 📋 Descripción del Proyecto

Proyecto desarrollado para el módulo **Dashboard & Análisis de Datos** del **Máster Data & Analytics de ThePowerMBA**. El análisis se aplica a la cadena de suministro de un centro logístico y parte de un dataset de pedidos ficticios creados ad hoc para este proyecto. El proyecto está íntegramente desarrollado en Microsoft Excel y cubre un proceso completo de ETL, análisis descriptivo, visualización mediante dashboard interactivo e informe ejecutivo de resultados.

El objetivo es identificar cuellos de botella, evaluar el rendimiento de proveedores y transportistas, y proporcionar recomendaciones basadas en datos para mejorar la eficiencia operativa.

---

## 🗂️ Estructura del Proyecto

```
📁 Proyecto_SupplyChain/
│
├── 📊 Dashboard_ThepowerMBA_ChristopherFdez.xlsx   # Archivo principal del proyecto
│   ├── 🗄️  Dataset Limpio          → Datos transformados y limpios (2.000 registros)
│   ├── 📈  Análisis Descriptivo    → KPIs, estadísticas y tablas de resumen
│   ├── 🔢  Analisis               → Tablas dinámicas y cálculos auxiliares
│   └── 📊  Dashboard              → Visualización interactiva (Excel)
│
├── 📄 Informe_Analisis_SupplyChain.docx            # Informe explicativo (Word)
└── 📖 README.md                                    # Este archivo
```

## 🛠️ Instalación y Requisitos

Este proyecto no requiere instalación de software adicional. Solo es necesario:

- **Microsoft Excel** (versión 2016 o superior, recomendado 365) para visualizar el dashboard y las tablas dinámicas con todas sus funcionalidades.
- **Microsoft Word** (versión 2016 o superior) para abrir el informe explicativo.

No se utilizan lenguajes de programación ni dependencias externas. Todo el procesamiento, análisis y visualización está contenido en el archivo `.xlsx`.

---

## 🔧 Fases del Proyecto

### 1. Transformación y Limpieza de Datos ✅
- Estandarización de fechas y tipos de datos
- Eliminación de duplicados y valores nulos
- Creación de variables derivadas:  `Año_Pedido`, `Mes_Pedido`,`Semana_Pedido`,`Desviación_Días`, `Flag_Incidencia`, `OTIF`, `Pct_Coste_Transporte`
- Normalización de campos
- Dataset final: **2.000 registros sin valores faltantes**

### 2. Análisis Descriptivo ✅
- Estadísticas descriptivas de variables numéricas (media, mediana, desviación típica, min/max)
- Resumen ejecutivo de KPIs globales
- Análisis por categoría de producto, proveedor, modo de transporte y almacén
- Distribución de incidencias y estados de pedido
- Comparativa interanual 2023 vs. 2024

### 3. Dashboard ✅
- Dashboard interactivo en Excel con segmentadores dinámicos
- Visualizaciones de KPIs en tiempo real
- Gráficos de líneas, circulares y tablas dinámicas
- Filtros por año, categoría, proveedor, almacén, modo de transporte, transportista e incidencias

### 4. Informe Explicativo ✅
- Documento Word estructurado con portada profesional
- 10 secciones: introducción, descripción del dataset, KPIs, análisis por categoría/proveedor/transporte/incidencias, evolución anual, rendimiento por almacén y conclusiones
- Tablas formateadas y recomendaciones accionables


---

## 📊 Principales Hallazgos

| KPI | Valor | Estado |
|-----|-------|--------|
| Total pedidos | 2.000 | — |
| Valor total gestionado | 502,3 M€ | — |
| Coste transporte / Valor | 4,98% | ✅ Bajo |
| OTIF global | 48,5% | **🔴 Crítico** |
| % Pedidos retrasados | 26,5% | **🟠 Elevado**|
| % Pedidos con incidencia | 57,6% | **🔴 Crítico** |
| Lead time medio | 15,1 días |

> ⚠️ **El OTIF del 48,5% es el hallazgo más crítico.** El estándar de la industria logística se sitúa por encima del 90%. Solo 1 de cada 2 pedidos se entrega a tiempo y en condiciones correctas.

---

## 🏷️ Variables del Dataset

| Variable | Tipo | Descripción |
|----------|------|-------------|
| `ID_Pedido` | Texto | Identificador único del pedido |
| `Fecha_Pedido` | Fecha | Fecha de emisión del pedido |
| `Año_Pedido` / `Mes_Pedido` | Numérico | Año y mes extraídos |
| `Proveedor` | Categórico | 10 proveedores distintos |
| `Categoría` | Categórico | 8 categorías: Maquinaria, Automoción, Electrónica, Farmacia, Construcción, Químicos, Alimentación, Textil |
| `Almacén_Destino` | Categórico | 6 almacenes: ZGZ, MAD-01, MAD-02, VAL, BCN, SEV |
| `Modo_Transporte` | Categórico | Camión FTL, Camión LTL, Ferroviario, Aéreo, Marítimo |
| `Valor_Total_EUR` | Numérico | Valor económico del pedido (€) |
| `Coste_Transporte_EUR` | Numérico | Coste de transporte asociado (€) |
| `Lead_Time_Días` | Numérico | Días entre pedido y entrega estimada |
| `Desviación_Días` | Numérico | Diferencia real vs. estimada (negativo = adelanto) |
| `OTIF` | Booleano | On Time In Full: TRUE si entregado a tiempo y sin incidencias |
| `Estado` | Categórico | Entregado / Retrasado / En almacén |
| `Incidencias` | Categórico | Ninguna / Error de cantidad / Daño en mercancía / Pérdida parcial / Documentación incompleta |

---

## 🔑 Conclusiones Clave

1. **OTIF crítico (48,5%):** La cadena de suministro opera muy por debajo del estándar del sector. Se requiere un plan de mejora urgente con objetivos trimestrales.

2. **Incidencias sistémicas (57,6%):** Los cuatro tipos de incidencia se distribuyen de forma uniforme (~25% cada uno), indicando problemas transversales, no puntuales.

3. **Deterioro entre años:** El OTIF bajó de 49,6% (2023) a 47,4% (2024) pese al aumento del volumen, señal de que la capacidad operativa no escala al ritmo del negocio.

4. **Maquinaria y Automoción concentran el 66,2% del valor:** Mejoras en estas categorías tienen el mayor retorno económico potencial.

5. **Transporte aéreo ineficiente:** Pese a ser el modo más costoso, registra el peor OTIF (43,7%), mientras que el marítimo obtiene el mejor (52,1%).

---

## 📬 Contacto

**Autor:** Christopher Fernández  
**Máster:** Data & Analytics — ThePowerMBA  
**Módulo:** Dashboard & Análisis de Datos  
**Período analizado:** Enero 2023 – Diciembre 2024  
**Dataset:** 2.000 pedidos · 28 variables · 6 almacenes · 10 proveedores  
