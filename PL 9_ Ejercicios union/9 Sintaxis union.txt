Nombre:_____________________________
Grupo:______________________________
Profesor: Edgar A. Catalán Salgado

EJERCICIOS UNION

select Col1, col2
from tabla1
union
select Col1,Col2
from tabla2
union
...
union
select Col1,Col2
from tabla

El operador union tiene 2 restricciones:
1.- todas las consultas tienen que tener el mismo numero de columnas
2.- La columna n en todas las consultas tiene que ser del mismo tipo, es decir, si en la consulta 1 la columna 1 es varchar, dicha columna tiene que ser varchar en todas las consultas 
3.- La clausal order by solo se puede utilizar hasta el final y aplica al conjunto resultado del operador union.


