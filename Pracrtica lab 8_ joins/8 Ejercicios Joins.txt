Nombre:_____________________________
Grupo:______________________________
Profesor: Edgar A. Catalán Salgado


EJERCICIOS JOINS


-- 1. MUESTRA A LOS PROVEEDORES CON LOS PRODUCTOS QUE SURTE

-- 2. MUESTRA TODOS LOS PROVEEDORES Y LOS PRODUCTOS QUE SURTEN (SI ES QUE SURTE)

-- 3. MESTRA TODOS LOS PRODUCTOS Y EL PROVEEDOR QUE LOS SURTE (SI LO SURTE ALGUNO)

-- 4. MUESTRA TODOS LOS PROVEEDORES Y TODOS LOS PRODUCTOS MOSTRANDO LOS PRODUCTOS QUE SURTE CADA PROVEEDOR

-- 5. MUESTRA EL NOMBRE DE LOS PRODUCTOS VENDIDOS

-- 6. MUESTRA EL NOMBRE DE LOS PRODUCTOS QUE NO SE HAN VENDIDO

-- 7. MUESTRA EL NOMBRE DE LOS CLIENTES QUE HAN COMPRADO ASI COMO LA FECHA EN QUE LO HICIERON

-- 8. MUESTRA EL NOMBRE DE LOS CLIENTES QUE NO HAN COMPRADO

-- 9. MUESTRA LA FECHA EN QUE SE VENDIERON LOS PRODUCTOS

-- 10. MUESTRA LOS PROVEEDORES DE LOS PRODUCTOS VENDIDOS

-- 11. MUESTRA LOS PROVEEDORES DE LOS PRODUCTOS QUE NO SE HAN VENDIDO

-- 12. MUESTRA LOS PRODUCTOS QUE HAN COMPRADO LOS CLIENTES

-- 13. ¿QUIENES HAN COMPRADO UN DVD?

-- 14. ¿QUIENES HAN COMPRADO ALGO DE SAMSUNG?

-- 15. ¿QUIENES NO HAN COMPRADO UN DVD?

-- 16. ¿QUIENES NO HAN COMPRADO ALGO DE SAMSUNG?

-- 17.- Muestra a todos los clientes junto con el total de ventas que se le han hecho, si todavia no compra debe aparecer cero 

-- 18.- Muestra el total de ventas hechas por delegacion

-- 19.- Muestra el total de productos vendidos por proveedor

-- 20.- Muestra las delegaciones con mas de 2 ventas

-- 21.- Muestra a los proveedores con mas de 3 productos

-- 22.- Muestra a los proveedores con mas de 3 productos vendidos

NON EQUIJOINS

-- 1. Es necesario clasificar a los clientes de acuerdo a su deuda de la siguiente forma:

/* 
Deuda			Clasificacion
0 		-> 	No Deudor
1-5000		->	Deudor Bajo
5001 - 15000	->	Deudor Medio
15001 o más	->	Deudor Alto

Sin embargo dado que los rangos pueden cambiar, y que probablemente se a–adan mas categorias, no se quieren dejar estos rangos fijos en las consultas de la aplicacion.

*/ 

Select TblClientes.Nombre, TblClientes.Deuda, TblTiposDeuda.Clasificacion
from tblClientes join TblTiposDeuda on TblClientes.Deuda Between TblTiposDeuda.LimInf and TblTiposDeuda.LimSup

TipoDeuda
IdTipoDeuda, Nombre, LimInf, LimSup
1, No deudor, 0, 0
2, Deudor Bajo,1, 5000
3, deudor medio, 5000, 25000
4, Deudor Alto, 25000, 500000000

2. Se desea clasificar a los clientes de acuerdo a su antigüedad en años para ofrecer premios especiales y beneficios de acuerdo a lo siguiente:

/*

0 - 1 Año	Cliente Nuevo	Sin Premio
2 - 4 Año	Cliente Medio	Premio Especial 1
5 ó más años	Cliente Bueno	Premio Especial 2

*/

3. Se desea clasificar a las ventas, para que de acuerdo a su monto total, se le regale al cliente una cuponera con descuentos y promociones, sin embargo debido a posibles cambios en los rangos y a que de acuerdo a la temporada cambien los premios añadiendo unos y quitando otros, se desesa no dejar fijos estos rangos en las consultas de la aplicacion

/*

0 - 10000		Venta baja		Cuponera Productos Basicos
10000 o mas		Venta media		Cuponera Productos de lujo

*/


-- SELF JOIN

-- 1. Muestra a los productos que cuestan mas que el DVD

-- 2. Muestra a los clientes con mas credito que edgar

-- 3. Muestra a los clientes con mas edad que edgar

-- 4. Muestra a los clientes de la misma delegacion que edgar

-- 5. Muestra las ventas realizadas el mismo dia que la venta con el idventa=2

-- 6. Muestra los clientes que sean de la misma delegacion que edgar y que tengan mas credito

-- 7. Muestra a los clientes con su respectivo aval

-- 8. Muestra a todos los clientes sin importar si tienen aval o no

-- 8. Muestra solo a los clientes que NO tienen aval

-- 9. Muestra solo a los clientes que son aval de otro cliente

 