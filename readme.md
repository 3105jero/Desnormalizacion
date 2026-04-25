# 📊 Desnormalización en Bases de Datos

![Database](https://img.shields.io/badge/Database-Design-blue)
![SQL](https://img.shields.io/badge/SQL-Optimization-green)
![Status](https://img.shields.io/badge/Status-Academic_Project-orange)

---

## 📌 ¿Qué es la desnormalización?

La **desnormalización** es una técnica de diseño de bases de datos en la que se rompe intencionalmente alguna de las formas normales (1NF, 2NF, 3NF o BCNF) con el objetivo de **mejorar el rendimiento de las consultas**.

A diferencia de la normalización (que busca eliminar redundancia), la desnormalización **introduce redundancia controlada** para optimizar la lectura de datos.

---

## 🎯 ¿Cuándo se usa?

Se utiliza principalmente cuando:

- Se prioriza la **velocidad de lectura** sobre la escritura  
- Se manejan grandes volúmenes de datos  
- Se construyen sistemas de análisis (BI, dashboards)  

---

## 🧪 Caso práctico: Sistema de Reporting (Data Warehouse)

En sistemas analíticos (OLAP), como dashboards empresariales, es común aplicar desnormalización.

---

### 🔹 Esquema normalizado (OLTP)

```sql
SELECT v.fecha, c.nombre, p.nombre, p.precio
FROM ventas v
JOIN clientes c ON v.id_cliente = c.id
JOIN productos p ON v.id_producto = p.id;
