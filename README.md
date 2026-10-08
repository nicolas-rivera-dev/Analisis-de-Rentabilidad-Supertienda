# Análisis de Rentabilidad Supertienda
Análisis de rentabilidad en Power BI sobre una cadena de ventas en Latinoamérica y el Caribe, presentado como dos data storytellings: Gestión de Precios/Ingresos y Gestión de Producto.

## Resumen ejecutivo

| Indicador | Valor |
|---|---|
| Ventas totales | 21,57 M |
| Margen global | ~10% |
| Líneas de pedido con pérdida | 26% (1 de cada 4) |
| Productos únicos | 1.909 |
| Productos con pérdida en al menos una transacción | 1.262 (66%) |

**Conclusión:** las ventas crecen, pero la ganancia no sigue el mismo ritmo. La causa principal es una política de descuentos que no considera el impacto en el margen.

---

## Dataset

`data/Supertienda.csv`: 10.254 registros (líneas de pedido), 5.120 pedidos, 22 países, 4 regiones (Norte, Centro, Sur, Caribe).

| Campo | Descripción |
|---|---|
| IdPedido, FechaPedido, FechaEnvio, MetodoEnvio | Datos del pedido |
| IdCliente, NombreCliente, Segmento | Cliente (Cliente, Empresa, Pequeña empresa) |
| Pais, Region | Ubicación |
| Categoria, Subcategoria, NombreProducto | Producto (3 categorías: Tecnología, Mobiliario, Material de oficina) |
| Ventas, Cantidad, Descuento, Ganancia | Métricas |

---

## Storytelling 1: Gestión de Precios/Ingresos

**Audiencia:** Director Comercial y equipo de Pricing.

**Conflicto:** el 26% de las ventas genera pérdida. Los descuentos superiores al 20% destruyen ganancia en todas las categorías. Mesas tiene el mayor descuento promedio (32,82%) y un margen de -8,75%.

**Dashboard (Power BI):**
- KPIs generales con alerta en pedidos con pérdida
- Dispersión descuento promedio vs. ganancia por subcategoría
- Barras por rango de descuento
- Línea temporal de ventas vs. ganancia
- Tabla con formato condicional por margen

**Insights**
1. Hay un umbral crítico en 20% de descuento: por encima, la ganancia es negativa de forma consistente.
2. Mesas destruye valor: el descuento más alto del portafolio y el peor margen.
3. El volumen enmascara la pérdida: subcategorías con ventas altas tienen rentabilidad negativa.

**Decisiones recomendadas**
1. Techo de descuento del 15%, con aprobación gerencial para excepciones.
2. Alerta de rentabilidad en tiempo real para vendedores antes de confirmar un descuento.
3. Incentivos comerciales basados en margen, no solo en volumen.

---

## Storytelling 2: Gestión de Producto

**Audiencia:** Gerente de Categorías y Director de Producto.

**Conflicto:** 2 de cada 3 productos han generado pérdida y siguen activos, consumiendo recursos logísticos y comerciales. El problema es estructural, no puntual.

**Dashboard (Power BI):**
- KPIs con productos con pérdida en rojo
- Top 10 / Bottom 10 de productos por ganancia
- Treemap de ganancia por categoría y subcategoría
- Matriz de margen por subcategoría con escala rojo/verde
- Dispersión ventas vs. ganancia

**Insights**
1. El problema está en condiciones sistémicas de precio y descuento, no en SKUs aislados.
2. Mobiliario vende mucho y gana casi nada (Mesas y Libreros con margen negativo).
3. Productos con ventas superiores a 100.000 aparecen con ganancia neta negativa.

**Decisiones recomendadas**
1. Auditoría inmediata del Bottom 10 (precio, costo de adquisición o descuento).
2. Revisión trimestral del portafolio: dos trimestres en pérdida activan el proceso de descontinuación.
3. Reasignar recursos comerciales y logísticos hacia el Top 10 más rentable.

---

## Estructura del repositorio

```
supertienda-data-storytelling/
├── README.md
├── data/
│   └── Supertienda.xlsx
├── dashboard/
│   └── Supertienda.pbix
├── docs/
│   └── Data_Storytelling.pdf
└── images/
    ├── storytelling_1_precios.png
    └── storytelling_2_producto.png
```

## Cómo usarlo

1. Descarga `dashboard/Supertienda.pbix` y ábrelo con Power BI Desktop.
2. Si Power BI pide la fuente de datos, apunta a `data/Supertienda.xlsx` (Transformar datos → Configuración de origen de datos).

## Herramientas

Power BI (DAX, formato condicional, visualizaciones) · Excel · Data Storytelling

## Autor

**Nicolas Rivera**: [GitHub](https://github.com/nicolas-rivera-dev)
