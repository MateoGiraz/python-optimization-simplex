[Ir al proyecto Colab](https://colab.research.google.com/drive/1Uqv9q-7wN0nB9nXq21e5SQRkpdaG0-wC?usp=sharing)

# Obligatorio de Optimización con álgebra Lineal
## Abastecimiento de demanda sobre red de transporte

![image](https://user-images.githubusercontent.com/100039777/208156883-07ec4303-fb1e-4fe7-b38f-b666426534b6.png)


La figura muestra una problema de abastecimiento ´optimo de la demanda, donde el producto
viaja sobre una red de transporte, bosquejada arriba.
- Las demandas di ⩾ 0, están asociadas a ubicaciones geográficas, indicadas por nodos. Son parámetros del problema.
- La producción pi también se asocia a nodos, y es una variable a optimizar, dentro de límites pi ∈ [0, pi]. Cada productor i tiene un costo ci por unidad de producto.
- Los enlaces i → j indican el transporte de mercadería, siendo yij la cantidad transportada en el sentido indicado por la flecha. El transporte puede ser en sentido contrario, en cuyo caso yij < 0. Cada enlace tiene restricciones de capacidad: |yij | ⩽ yij .
- En cada nodo hay balance de flujo: la cantidad que entra debe ser igual a la que sale.
- Para cada grupo se especificará un conjunto diferente de parámetros.

## Se pide:
- (a) Expresar como programación lineal el problema de abastecer la demanda con costo mínimo y en forma consistente con las restricciones. Identificar el vector de variables, y expresar las restricciones de igualdad y desigualdad.
- (b) Hacer un script de python en el cual se ingresan los vectores de parámetros c, d, ¯p, ¯y, y devuelve el costo óptimo y los valores de las variables de decisión.
- (c) Suponiendo inicialmente que no hay límites de producción p1, y con los valores dados de yij , encontrar el máximo valor de d0 (hasta un dígito decimal de precisión) para el cual el problema es factible. Para una serie representativa de valores de d0 entre 0 y el máximo hallado, resolver la optimización. Graficar la evolución del costo al crecer d0. Comentar los resultados.
- (d) Si ahora la producción máxima en el nodo 1 es ¯p1 dado, evaluar como se modifican los resultados de (c).
- (e) Volviendo al caso de (c), sin límites de producción, se plantea mejorar el transporte agregando un enlace nuevo entre dos nodos a determinar, de la misma capacidad que los anteriores. No se admite duplicar enlaces existentes. Proponer cual enlace agregar buscando agrandar lo más posible región de factibilidad en (c), y al menor costo. Se puede intentar con ensayo y error, explicar el razonamiento.
- (f) Repetir el resto del análisis de (c) con la nueva red de (e). Explicar los resultados.
- (g) Agregando la restricción de producción máxima ¯p1 como en (d), repetir el análisis para la nueva red de (e). Explicar los resultados.

## Datos:

- yij = 100 unidades, para todo enlace i→j.
- Solo los nodos 1 y 3 están habilitados para la producción. Los restantes se eliminan del problema. p3 no tiene límite de cantidad, el límite p1 se describe abajo. Los costos de producción son c1= 1, c3= 7.
- La producción máxima en el nodo 1 es ̄p1= 100.
- El nodo 1 no tiene demanda, d1= 0. Los restantes tendrán demandas iguales di=d0, exploraremos diferentes valores del parámetro d0.
