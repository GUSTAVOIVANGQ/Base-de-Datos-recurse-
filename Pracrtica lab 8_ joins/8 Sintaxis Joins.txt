Nombre:_____________________________
Grupo:______________________________
Profesor: Edgar A. Catalán Salgado


EJERCICIOS JOINS


La clausula join nos permite unir 2 tablas bajo un determinado criterio, nos sirve para juntar la informacion almacenada en los campos de una tabla con los de otra

un join se especifica en la seccion del from:

select Tabla1.Campo, Tabla2.Campo
from Tabla1 aliasTabla1 join tabla2 aliastabla2 on condicion

En la parte del select especificamos la tabla a la que pertenece el campo principalmete para evitar ambiguedades en el caso de que 2 tablas posean campos con el mismo nombre (por ejemplo el campo nombre de la tabla proveedores y el campo nombre de la tabla productos), ademas de esta forma se da mas claridad a la consulta.

Los alias permiten cambiar, por asi decirlo, el nombre de una tabla en la consulta, Si se le pone un alias a una de las tablas, se tiene que dejar de usar el nombre de la tabla y forzosamente para esa tabla tenemos que usar el alias.

De acuerdo a la condicion del join podemos tener los siguientes tipos de join

EQUIJOIN, es cuando en la condicion se pide que se cumpla una igualdad, generalmente es de una llave primaria con una llave foranea.

select Tabla1.Campo, Tabla2.Campo
from Tabla1 join tabla2 on Tabla1.CampoLlavePrim=Tabla2.CampoLLaveForanea


NON EQUIJOINS, es cuando en la condicion no se pide una igualdad, una posibilidad es cuando se compara un valor de una de las tablas con un rango establecido en una de las otras

select Tabla1.Campo, Tabla2.Campo
from Tabla1 join tabla2 on 
Tabla1.Dato>Tabla2.LimInf and Tabla1.Dato<Tabla2.LimSup

Si tabla1 y tabla2 son la misma tabla, entonces se dice que se esta haciendo un SELF JOIN, en este caso en particular se hace obligatorio el uso del alias para tablas:

El join solo muestra los registros que cumplen con la relacion establecida mediante la condicion, todos los registros de ambas tablas que no puedan cumplir con dicha condicion quedan fuera, por esta razon es que se conocen como INNER JOINS o joins internos. 

Debido a que es muy comun los casos en que necesitemos todos los registros de una de las dos tablas o incluso de las 2, existen los OUTER JOINS,que nos permiten agregar estos registros, estos son:

LEFT OUTER JOIN
RIGHT OUTER JOIN

o simplemente:

LEFT JOIN
RIGHT JOIN


Estos en pocas palabras, si nos posicionamos en la palabra join, tenemos una tabla a la izquierda y otra a la derecha, mediante LEFT o RIGHT indicamos de cual de las tablas queremos todos los registros.


select Tabla1.Campo, Tabla2.Campo
from TablaIzquierda left join tablaDerecha on condicion
 

ANIDAMIENTO DE JOINS

La instruccion completa de un join nos da como resultado una tabla que contiene todos los campos de las tablas usadas, ese resultado puede ser usado como parametro para otro join, lo cual nos permite hacer cosas como:

select Tabla1.Campo, Tabla2.Campo, Tabla3.Campo
from (Tabla1 join Tabla2 on condicion1)
      join Tabla3 on Condicion2


select Tabla1.Campo, Tabla2.Campo, Tabla3.Campo, Tabla4.Campo
from (Tabla1 join Tabla2 on condicion1)
      join 
     (Tabla3 join Tabla4 on Condicion2)
      on condicion3



-- 1. MUESTRA A LOS PROVEEDORES CON LOS PRODUCTOS QUE SURTE
   select proveedor.nombre, producto.nombre
   from proveedor join producto on proveedor.idproveedor= producto.idproveedor

-- 2. MUESTRA TODOS LOS PROVEEDORES Y LOS PRODUCTOS QUE SURTEN (SI ES QUE SURTE)
   select proveedor.nombre, producto.nombre
   from proveedor left join producto on proveedor.idproveedor= producto.idproveedor

-- 3. MESTRA TODOS LOS PRODUCTOS Y EL PROVEEDOR QUE LOS SURTE (SI LO SURTE ALGUNO)
   select proveedor.nombre, producto.nombre
   from proveedor right join producto on proveedor.idproveedor= producto.idproveedor

-- 4. MUESTRA TODOS LOS PROVEEDORES Y TODOS LOS PRODUCTOS MOSTRANDO LOS PRODUCTOS QUE SURTE CADA PROVEEDOR
   select proveedor.nombre, producto.nombre
   from proveedor full join producto on proveedor.idproveedor= producto.idproveedor

