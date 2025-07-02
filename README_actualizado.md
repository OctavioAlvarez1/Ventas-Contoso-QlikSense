# 📊 Contoso Sales Analytics Dashboard

Este proyecto fue desarrollado en Qlik Sense como parte del Bootcamp de Jupi Digital. Tiene como finalidad construir una solución de inteligencia de negocios basada en el caso realista de Contoso, una empresa multinacional con estructura compleja, múltiples niveles de operación y una fuerza laboral global y móvil.

---

## 🧠 Contexto de Negocio

Contoso es una empresa con presencia internacional y la siguiente estructura organizacional:

- 🏢 **Headquarters**: sede central en París, con 25.000 empleados, incluyendo áreas administrativas, ingeniería y centros de datos.
- 🌍 **Centros Regionales**: conectados a la sede mediante WAN de alto ancho de banda, con foco en ventas y soporte.
- 🏬 **Oficinas Satélite**: representación local con el 80% del personal de ventas y soporte técnico. Conectadas a los centros regionales.

🔁 **El 25% de la fuerza laboral es exclusivamente móvil**, por lo que proporcionar soporte remoto optimizado es un objetivo clave.

**Retos técnicos identificados:**

- Diversidad geográfica con distintas normativas locales.
- Uso mixto de dispositivos (Windows, Mac, Linux, iOS, Android).
- Necesidad de seguridad para proteger datos confidenciales y propiedad intelectual.
- Alta demanda de analítica comercial para tomar decisiones en tiempo real.

---

## 🎯 Objetivos del Dashboard

El equipo comercial de Contoso definió los siguientes indicadores y necesidades para la solución de BI:

- **Indicadores clave**:
  - Sales Amount (monto de ventas)
  - Gross Margin (margen bruto)
  - Net Margin (margen neto)
  - Sales Quantity (cantidad vendida)
  - Budget Amount (presupuesto de ventas)

- **Visualizaciones requeridas**:
  - Variación % vs mismo mes del año anterior
  - Cumplimiento de presupuesto
  - Gráfico de tendencia mensual de ventas y márgenes (últimos 12 meses)
  - Mapa de clientes con mayor margen neto
  - Resumen por jerarquía de producto, país, y cliente
  - Análisis YTD vs Net Margin

---

## 🗂️ Datos Utilizados

- Hechos:
  - Ventas Online
  - Ventas en Tienda
  - Presupuesto

- Dimensiones:
  - Productos, Categorías, Subcategorías
  - Clientes, Tiendas, Territorios, Geografía
  - Segmentación RFM

- Fecha:
  - Calendario Maestro generado dinámicamente

---

## 🧪 Transformación y Modelado

- Se aplicó un modelo en estrella.
- Scripts personalizados en Qlik Sense:
  - Uso de `LEFT JOIN`, `LOAD precedentes`, `GROUP BY`
  - Agregaciones (`SUM`, `Net Margin`, `Gross Margin`)
  - Renombramiento de claves, prevención de sintéticas
  - Calendario completo con `MAKEDATE`, `RECNO`, `MONTHSTART`

---

## 📈 Dashboards y Visualizaciones

### 🔹 Dashboard General
![Dashboard General](Imagenes/Ventas_Contoso.png)

### 🔹 Análisis por Tiendas
![Tiendas](Imagenes/Tiendas.png)

### 🔹 Análisis por Clientes
![Clientes](Imagenes/Clientes.png)

### 🔹 Análisis por Productos
![Productos](Imagenes/Productos.png)

Cada sección incluye KPIs dinámicos, filtros por periodo, moneda y tipo de análisis, además de visualizaciones interactivas como gráficos de dispersión, barras jerárquicas y mapas de calor.

---


---

## 📊 Insights y Hallazgos de Negocio

A partir del análisis exploratorio con Qlik Sense, se destacan los siguientes hallazgos:

### 1. Evolución de Ventas y Márgenes

- Las ventas muestran una caída del **-3,9 % en abril vs. marzo**, tras una tendencia creciente en Q1.
- El **margen neto acumulado YTD es del 49 %**, con €544,8 M sobre €1,1 B en ventas.

📌 *Recomendación:* reforzar campañas promocionales en mayo-junio para sostener el run-rate proyectado anual (>€3 B).

---

### 2. Desempeño por País

| País      | Ventas Abr-24 | Margen Neto | % Margen |
|-----------|----------------|-------------|----------|
| Alemania  | € 28,4 M       | € 10,7 M    | 37 %     |
| Armenia   | €  8,4 M       | €  4,3 M    | 51 %     |
| Australia | € 25,3 M       | € 12,9 M    | 51 %     |

- Algunos mercados con menor volumen presentan **márgenes significativamente mayores**.
- **Alemania** y otros países de alto volumen tienen margen inferior al promedio.

📌 *Recomendación:* replicar tácticas comerciales de países de alto margen en mercados prioritarios.

---

### 3. Análisis por Productos

- Los productos más vendidos en abril fueron:
  - 📱 Móviles: 667k unidades
  - 💻 PCs/Laptops: 433k unidades
  - 🔌 Electrodomésticos: 416k unidades

- Las **Cámaras y Videograbadoras** se destacan por su **alto margen neto**, a pesar del bajo volumen.

📌 *Recomendación:* promocionar bundles de alto margen e identificar productos con baja rentabilidad para descontinuación.

---

### 4. Perfil de Clientes

- Más del **90 % de ventas proviene del segmento corporativo**.
- El análisis RFM muestra potencial para reactivar clientes inactivos (“Hibernating”).

📌 *Recomendación:* lanzar campañas de recuperación con ofertas personalizadas y explorar mayor presencia B2C.

---

### 5. Prioridades para el negocio (Q2 2024)

1. Restablecer el crecimiento mensual de ventas.
2. Optimizar el mix de producto hacia categorías de mayor rentabilidad.
3. Replicar prácticas exitosas de mercados de alto margen.
4. Activar campañas segmentadas por perfil de cliente.

---

## 👥 Público Objetivo

- Dirección Comercial
- Marketing y Ventas
- Planificación Estratégica

Este dashboard está diseñado para ofrecer insights ágiles y confiables para la toma de decisiones de negocio a distintos niveles organizacionales.

---

## 🛠️ Stack Tecnológico

- Qlik Sense SaaS
- QVDs para staging y almacenamiento intermedio
- Transformaciones avanzadas en script editor
- Visualizaciones customizadas y KPIs inteligentes

---

## ✍️ Autor

Desarrollado por **Octavio Alvarez**  
Bootcamp Qlik Sense – **Jupi Digital**

---

## 📎 Referencia

- Caso Contoso:  
  https://learn.microsoft.com/es-es/microsoft-365/enterprise/contoso-overview?view=o365-worldwide
