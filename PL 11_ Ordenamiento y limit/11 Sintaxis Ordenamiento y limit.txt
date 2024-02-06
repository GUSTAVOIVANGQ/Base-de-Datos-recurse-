

ORDENAMIENTO
El ordenamiento de los registros se hace mediante la clausula order by esta se pone al final se la consulta

select campo1, campo2..
from tabla
where condicion
order by tituloColumna1 ASC/DESC, tituloColumna2 ASC/DESC...

TituloColumna es la col con la cual vamos a ordenar

Ejemplo
--Ordena los clientes por nombre en orden descendente
select nombre
from tblClientes
order by nombre


LIMITE DE REGISTROS

Se puede establecer un limite de registros a mostrar.Una vez establecido dicho limite, la consulta regresara la cantidad de registros indicados.

select campo1, campo2
from tblClientes
where condicion
limit  Cantidad [offset posinicial]

Donde Cantidad es el numero de registros que se desean y la posicion inicial a partir de que registro se va a obtener


Ejemplo
-- muestra al primer cliente registrado
select nombre
from tblClientes
limit 1
