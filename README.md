Ejercicio 1
SELECT * FROM productos;

Ejercicio 2
SELECT * FROM productos
WHERE categoria = 'Ropa';

Ejercicio 3
SELECT nombre, categoria, precio_usd FROM productos
WHERE precio_usd > 50;

Ejercicio 4
SELECT nombre, categoria FROM productos
WHERE stock = 0;

Ejercicio 5
SELECT nombre, ciudad, edad FROM clientes
WHERE pais = 'Colombia' AND edad > 25;

Ejercicio 6
SELECT * FROM productos
WHERE marca IN ('SportMax','TechFit');

Ejercicio 7
SELECT * FROM productos
WHERE nombre LIKE '%deportiv%' OR nombre LIKE '%running%';

Ejercicio 8
SELECT * FROM productos
ORDER BY precio_usd DESC
LIMIT 5;

Ejercicio 9
SELECT id_orden, fecha_compra, monto_total FROM ordenes
ORDER BY fecha_compra DESC
LIMIT 3;

Ejercicio 10
SELECT * FROM clientes
WHERE fecha_alta >= '2024-03-01' AND fecha_alta <= '2024-05-30';

Ejercicio 11
SELECT categoria, COUNT(*) AS total_productos
FROM productos
GROUP BY categoria
ORDER BY total_productos DESC;

Ejercicio 12
SELECT categoria, ROUND(AVG(precio_usd),2) AS precio_promedio
FROM productos
GROUP BY categoria
ORDER BY precio_promedio DESC;

Ejercicio 13
SELECT estado, ROUND(SUM(monto_total),2) AS monto_total_estado
FROM ordenes
GROUP BY estado
ORDER BY monto_total_estado DESC;

Ejercicio 14
SELECT MIN(precio_usd) AS precio_minimo, MAX(precio_usd) AS precio_maximo, ROUND(AVG(precio_usd),2) AS precio_promedio
FROM productos
WHERE activo = 1

Ejercicio 15
SELECT pais, COUNT(*) AS total_clientes, AVG(edad) AS edad_promedio
FROM clientes
GROUP BY pais
HAVING COUNT(*)>1
ORDER BY total_clientes DESC
