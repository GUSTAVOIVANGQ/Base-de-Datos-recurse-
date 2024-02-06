Nombre:_____________________________
Grupo:______________________________
Profesor: Edgar A. Catalán Salgado

EJERCICIOS UNION


/*****************
1. Muestra a los Clientes con su Delegación, pero por razones de espacio reemplaza las 
siguientes:


Gustavo A. Madero - GAM
Benito Juárez - B. Juarez
Alvaro Obregon - A. Obregon
****************/

Select nombre, replace (Delegacion, 'Gustavo A. Madero', 'GAM')
from cliente
where delegacion= 'Gustavo A. Madero'
Union
Select nombre, replace (Delegacion, 'Benito Juarez', 'B. Juarez')
from cliente
where delegacion= 'Benito Juarez'
Union
Select nombre, replace (Delegacion, 'Alvaro Obregon', 'A. Obregon')
from cliente
where delegacion= 'Alvaro Obregon'
union
Select nombre, delegacion
from cliente
where delegacion not in ('Gustavo A. Madero', 'Benito Juarez', 'Alvaro Obregon');



/******************
2. Es necesario clasificar a los clientes de acuerdo a su deuda de la siguiente forma:

 

0 			-> 	No Deudor
1-5000		->	Deudor Bajo
5001 - 15000	->	Deudor Medio
15001 o más	->	Deudor Alto

**********************/


/*************************
 3. Se desea clasificar a los clientes de acuerdo a su antigüedad en años para ofrecer un premio especial de acuerdo a lo siguiente:



0 - 1 Año	Cliente Nuevo	Sin Premio
2 - 4 Año	Cliente Medio	Premio Especial 1
5 ó más años	Cliente Bueno	Premio Especial 2

**************************/



/************************* 4. Para compatibilidad con un Software especial se necesita obtener los datos del cliente con el identificador 1 de la siguiente
forma:

	1. Id_Cliente
	2. Nombre
	3. ApPaterno
	4. ApMaterno
	5. Credito
	6. Deuda
***************************/


/**************************
5. Se desea el siguiente reporte

NOmbre		|	Tipo		  |	Deuda
Edgar Catalan	|	Cliente	  |	5000
Lg			|	Proveedor	  |	N/A
...

***************************/


/***************************
6. Se desea el siguiente reporte para la delegacion iztapalapa

 Delegacion	|  Dato				|Valor
 Iztapalapa	|  ---				|---
 ---			| Deuda	Menor		| 15000
 ---			| Deuda Promedio		| 38000
 ---			| Deuda Mayor			| 55000
 ---			| Total Deuda			|150000
 ---			| Credito Menor		| 25000
 ---			| Credito Promedio		| 43000
 ---			| Credito Mayor		| 60000
 ---			| Numero de clientes	| 5


/*
 ---		|	

7. Se desea mostra los datos de la venta con el identificador 1 de la siguiente forma

No Venta	|Fecha		| Articulo	| Cantidad	| Precio
1		|2013/03/12	|  ---		|   ---		|  ---
1		|---			|Television	|    1		|  5000
1		|---			|dvd			|    2		|  2000
1		|---			|Total		|   ---		|  9000

*/


/*
8. Se desea mostrar los datos de la venta con el identificador 1 de la siguiente forma:

No Venta	|Cliente				|Fecha		| Articulo	| Cantidad	| Precio
1		|Edgar Catalan			|2013/03/12	|  ---		|   ---		|  ---
1		| ---				|---			|Television	|    1		|  5000
1		| ---				|---			|dvd			|    2		|  2000
1		| ---				|---			|Total		|   ---		|  9000



